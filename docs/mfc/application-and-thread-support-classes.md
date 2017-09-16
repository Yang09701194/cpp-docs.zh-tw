---
title: Application and Thread Support Classes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.support
dev_langs:
- C++
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 78d1c48f6b07999a1736bb443d1b1e31b2454cac
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="application-and-thread-support-classes"></a>Application and Thread Support Classes
Each application has one and only one application object; this object coordinates other objects in the running program and is derived from `CWinApp`.  
  
 The Microsoft Foundation Class (MFC) Library supports multiple threads of execution within an application. All applications must have at least one thread; the thread used by your `CWinApp` object is this primary thread.  
  
 `CWinThread` encapsulates a portion of the operating system's threading capabilities. To make using multiple threads easier, MFC also provides synchronization object classes to provide a C++ interface to Win32 synchronization objects.  
  
## <a name="application-and-thread-classes"></a>Application and Thread Classes  
 [CWinApp](../mfc/reference/cwinapp-class.md)  
 Encapsulates the code to initialize, run, and terminate the application. You will derive your application object from this class.  
  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 The base class for all threads. Use directly, or derive a class from `CWinThread` if your thread performs user-interface functions. `CWinApp` is derived from `CWinThread`.  
  
## <a name="synchronization-object-classes"></a>Synchronization Object Classes  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Base class of the synchronization object classes.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 A synchronization class that allows only one thread within a single process to access an object.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 A synchronization class that allows between one and a specified maximum number of simultaneous accesses to an object.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 A synchronization class that allows only one thread within any number of processes to access an object.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 A synchronization class that notifies an application when an event has occurred.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 Used in member functions of thread-safe classes to lock on one synchronization object.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 Used in member functions of thread-safe classes to lock on one or more synchronization objects from an array of synchronization objects.  
  
## <a name="related-classes"></a>Related Classes  
 [CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)  
 Parses the command line with which your program was started.  
  
 [CWaitCursor](../mfc/reference/cwaitcursor-class.md)  
 Puts a wait cursor on the screen. Used during lengthy operations.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Handles persistent storage of docking state data for control bars.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 Maintains the most recently used (MRU) file list.  
  
## <a name="see-also"></a>See Also  
 [Class Overview](../mfc/class-library-overview.md)


