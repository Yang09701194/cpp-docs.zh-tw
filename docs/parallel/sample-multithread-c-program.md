---
title: 多執行緒 C 程式的範例 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4706f6cd-ff9c-4dbf-99a2-1c999b568f17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29f29f94e9911ee6cd3a1f5377fee4fb9b84cda4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428577"
---
# <a name="sample-multithread-c-program"></a>多執行緒 C 程式範例

Bounce.c 是建立新的範例多執行緒程式執行緒的每個時間字母`a`或`A`型別。 每個執行緒會不斷在螢幕上不同顏色的快樂臉。 最多 32 個執行緒可以建立。 程式的正常終止，就會發生時`q`或`Q`型別。 如需編譯和連結 Bounce.c 的詳細資訊，請參閱[編譯和連結多執行緒程式](compiling-and-linking-multithread-programs.md)。

## <a name="example"></a>範例

### <a name="code"></a>程式碼

```c
// sample_multithread_c_program.c
// compile with: /c
//
//  Bounce - Creates a new thread each time the letter 'a' is typed.
//  Each thread bounces a happy face of a different color around
//  the screen. All threads are terminated when the letter 'Q' is
//  entered.
//

#include <windows.h>
#include <stdlib.h>
#include <string.h>
#include <stdio.h>
#include <conio.h>
#include <process.h>

#define MAX_THREADS  32

// The function getrandom returns a random number between
// min and max, which must be in integer range.
#define getrandom( min, max ) (SHORT)((rand() % (int)(((max) + 1) - \
                               (min))) + (min))

int main( void );                    // Thread 1: main
void KbdFunc( void  );               // Keyboard input, thread dispatch
void BounceProc( void * MyID );      // Threads 2 to n: display
void ClearScreen( void );            // Screen clear
void ShutDown( void );               // Program shutdown
void WriteTitle( int ThreadNum );    // Display title bar information

HANDLE  hConsoleOut;                 // Handle to the console
HANDLE  hRunMutex;                   // "Keep Running" mutex
HANDLE  hScreenMutex;                // "Screen update" mutex
int     ThreadNr;                    // Number of threads started
CONSOLE_SCREEN_BUFFER_INFO csbiInfo; // Console information

int main() // Thread One
{
    // Get display screen information & clear the screen.
    hConsoleOut = GetStdHandle( STD_OUTPUT_HANDLE );
    GetConsoleScreenBufferInfo( hConsoleOut, &csbiInfo );
    ClearScreen();
    WriteTitle( 0 );

    // Create the mutexes and reset thread count.
    hScreenMutex = CreateMutex( NULL, FALSE, NULL );  // Cleared
    hRunMutex = CreateMutex( NULL, TRUE, NULL );      // Set
    ThreadNr = 0;

    // Start waiting for keyboard input to dispatch threads or exit.
    KbdFunc();

    // All threads done. Clean up handles.
    CloseHandle( hScreenMutex );
    CloseHandle( hRunMutex );
    CloseHandle( hConsoleOut );
}

void ShutDown( void ) // Shut down threads
{
    while ( ThreadNr > 0 )
    {
        // Tell thread to die and record its death.
        ReleaseMutex( hRunMutex );
        ThreadNr--;
    }

    // Clean up display when done
    WaitForSingleObject( hScreenMutex, INFINITE );
    ClearScreen();
}

void KbdFunc( void ) // Dispatch and count threads.
{
    int         KeyInfo;

    do
    {
        KeyInfo = _getch();
        if ( tolower( KeyInfo ) == 'a' &&
             ThreadNr < MAX_THREADS )
        {
            ThreadNr++;
            _beginthread( BounceProc, 0, &ThreadNr );
            WriteTitle( ThreadNr );
        }
    } while( tolower( KeyInfo ) != 'q' );

    ShutDown();
}

void BounceProc( void *pMyID )
{
    char    MyCell, OldCell;
    WORD    MyAttrib, OldAttrib;
    char    BlankCell = 0x20;
    COORD   Coords, Delta;
    COORD   Old = {0,0};
    DWORD   Dummy;
    char    *MyID = (char*)pMyID;

    // Generate update increments and initial
    // display coordinates.
    srand( (unsigned int) *MyID * 3 );

    Coords.X = getrandom( 0, csbiInfo.dwSize.X - 1 );
    Coords.Y = getrandom( 0, csbiInfo.dwSize.Y - 1 );
    Delta.X = getrandom( -3, 3 );
    Delta.Y = getrandom( -3, 3 );

    // Set up "happy face" & generate color
    // attribute from thread number.
    if( *MyID > 16)
        MyCell = 0x01;          // outline face
    else
        MyCell = 0x02;          // solid face
    MyAttrib =  *MyID & 0x0F;   // force black background

    do
    {
        // Wait for display to be available, then lock it.
        WaitForSingleObject( hScreenMutex, INFINITE );

        // If we still occupy the old screen position, blank it out.
        ReadConsoleOutputCharacter( hConsoleOut, &OldCell, 1,
                                    Old, &Dummy );
        ReadConsoleOutputAttribute( hConsoleOut, &OldAttrib, 1,
                                    Old, &Dummy );
        if (( OldCell == MyCell ) && (OldAttrib == MyAttrib))
            WriteConsoleOutputCharacter( hConsoleOut, &BlankCell, 1,
                                         Old, &Dummy );

        // Draw new face, then clear screen lock
        WriteConsoleOutputCharacter( hConsoleOut, &MyCell, 1,
                                     Coords, &Dummy );
        WriteConsoleOutputAttribute( hConsoleOut, &MyAttrib, 1,
                                     Coords, &Dummy );
        ReleaseMutex( hScreenMutex );

        // Increment the coordinates for next placement of the block.
        Old.X = Coords.X;
        Old.Y = Coords.Y;
        Coords.X += Delta.X;
        Coords.Y += Delta.Y;

        // If we are about to go off the screen, reverse direction
        if( Coords.X < 0 || Coords.X >= csbiInfo.dwSize.X )
        {
            Delta.X = -Delta.X;
            Beep( 400, 50 );
        }
        if( Coords.Y < 0 || Coords.Y > csbiInfo.dwSize.Y )
        {
            Delta.Y = -Delta.Y;
            Beep( 600, 50 );
        }
    }
    // Repeat while RunMutex is still taken.
    while ( WaitForSingleObject( hRunMutex, 75L ) == WAIT_TIMEOUT );
}

void WriteTitle( int ThreadNum )
{
    enum {
        sizeOfNThreadMsg = 80
    };
    char    NThreadMsg[sizeOfNThreadMsg];

    sprintf_s( NThreadMsg, sizeOfNThreadMsg,
               "Threads running: %02d.  Press 'A' "
               "to start a thread,'Q' to quit.", ThreadNum );
    SetConsoleTitle( NThreadMsg );
}

void ClearScreen( void )
{
    DWORD    dummy;
    COORD    Home = { 0, 0 };
    FillConsoleOutputCharacter( hConsoleOut, ' ',
                                csbiInfo.dwSize.X * csbiInfo.dwSize.Y,
                                Home, &dummy );
}
```

### <a name="input"></a>輸入

```
a
q
```

## <a name="see-also"></a>另請參閱

[使用 C 和 Win32 進行多執行緒處理](multithreading-with-c-and-win32.md)