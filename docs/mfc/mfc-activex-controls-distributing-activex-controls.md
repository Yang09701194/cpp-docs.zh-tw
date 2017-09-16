---
title: 'MFC ActiveX Controls: Distributing ActiveX Controls | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], ANSI or Unicode versions
- RegSvr32.exe
- MFC ActiveX controls [MFC], distributing
- distributing MFC ActiveX controls
- redistributable files, MFC ActiveX controls
- GetSystemDirectory method [MFC]
- registering ActiveX controls
- MSVCRT40.dll
- registry [MFC], registering controls
- LoadLibrary method, registering ActiveX controls
- MFC40U.DLL
- MFC40.DLL
- GetWindowsDirectory method [MFC]
- installing ActiveX controls
- GetProcAddress method, registering ActiveX controls
- MFC ActiveX controls [MFC], installing
- MFC ActiveX controls [MFC], registering
- registering controls
- OLEPRO32.DLL
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
caps.latest.revision: 11
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
ms.openlocfilehash: a531f3a004729f5f877ec46205c187b77a31697e
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX Controls: Distributing ActiveX Controls
This article discusses several issues related to redistributing ActiveX controls:  
  
-   [ANSI or Unicode Control Versions](#_core_ansi_or_unicode_control_versions)  
  
-   [Installing ActiveX Controls and Redistributable DLLs](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [Registering Controls](#_core_registering_controls)  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI or Unicode Control Versions  
 You must decide whether to ship an ANSI or Unicode version of the control, or both. This decision is based on portability factors inherent in ANSI and Unicode character sets.  
  
 ANSI controls, which work on all Win32 operating systems, allow for maximum portability between the various Win32 operating systems. Unicode controls work on only Windows NT (version 3.51 or later), but not on Windows 95 or Windows 98. If portability is your primary concern, ship ANSI controls. If your controls will run only on Windows NT, you can ship Unicode controls. You could also choose to ship both and have your application install the version most appropriate for the user's operating system.  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> Installing ActiveX Controls and Redistributable DLLs  
 The setup program you provide with your ActiveX controls should create a special subdirectory of the Windows directory and install the controls' .OCX files in it.  
  
> [!NOTE]
>  Use the Windows **GetWindowsDirectory** API in your setup program to obtain the name of the Windows directory. You may want to derive the subdirectory name from the name of your company or product.  
  
 The setup program must install the necessary redistributable DLL files in the Windows system directory. If any of the DLLs are already present on the user's machine, the setup program should compare their versions with the versions you are installing. Reinstall a file only if its version number is higher than the file already installed.  
  
 Because ActiveX controls can be used only in OLE container applications, there is no need to distribute the full set of OLE DLLs with your controls. You can assume that the containing application (or the operating system itself) has the standard OLE DLLs installed.  
  
##  <a name="_core_registering_controls"></a> Registering Controls  
 Before a control can be used, appropriate entries must be created for it in the Windows registration database. Some ActiveX control containers provide a menu item for users to register new controls, but this feature may not be available in all containers. Therefore, you may want your setup program to register the controls when they are installed.  
  
 If you prefer, you can write your setup program to register the control directly instead.  
  
 Use the **LoadLibrary** Windows API to load the control DLL. Next, use **GetProcAddress** to obtain the address of the "DllRegisterServer" function. Finally, call the `DllRegisterServer` function. The following code sample demonstrates one possible method, where `hLib` stores the handle of the control library, and `lpDllEntryPoint` stores the address of the "DllRegisterServer" function.  
  
 [!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]  
  
 The advantage of registering the control directly is that you do not need to invoke and load a separate process (namely, REGSVR32), reducing installation time. In addition, because registration is an internal process, the setup program can handle errors and unforeseen situations better than an external process can.  
  
> [!NOTE]
>  Before your setup program installs an ActiveX control, it should call **OleInitialize**. When your setup program is finished, call **OleUnitialize**. This ensures that the OLE system DLLs are in the proper state for registering an ActiveX control.  
  
 You should register MFCx0.DLL.  
  
## <a name="see-also"></a>See Also  
 [MFC ActiveX Controls](../mfc/mfc-activex-controls.md)


