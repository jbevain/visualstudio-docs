---
title: "Extending and Customizing Tool Windows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "user interfaces, essentials"
  - "tool windows, standard"
ms.assetid: 46b2892e-7b2b-4b3f-83a7-b884f1e114ee
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Extending and Customizing Tool Windows
Visual Studio provides several different types of windows, for example tool windows, document windows, and dialog windows. Other windows such as the Properties window, the Output window, and the Task List window, are types of tool windows.  
  
## Tool Windows  
 Visual Studio tool windows are usually read-only windows that are not file-based. In this they differ from document windows, which display files in read-write mode. The **Toolbox**, **Solution Explorer**, **Properties** window, and **Web Browser** are examples of tool windows.  
  
 To find out how to create a simple tool window, see [Adding a Tool Window](../extensibility/adding-a-tool-window.md).  
  
 To register a tool window with Visual Studio, see [Registering a Tool Window](../extensibility/registering-a-tool-window.md).  
  
 Tool windows are single-instance by default, meaning that only one instance of the tool window can be open at a time. After a single-instance tool window is opened, it remains open until the IDE is closed. When you close a single-instance tool window, only its visibility changes. You can also create multi-instance tool windows, such that multiple instances of the window can be open simultaneously. See [Creating a Multi-Instance Tool Window](../extensibility/creating-a-multi-instance-tool-window.md) for more information.  
  
 Tool windows can be *dynamic*, meaning that they are visible whenever their related UI context applies. The use of auto-visibility can reduce the clutter of windows in the IDE. For more information, see [Opening a Dynamic Tool Window](../extensibility/opening-a-dynamic-tool-window.md).  
  
 Tool windows can be docked, floating, or tabbed in the document frame. The tool window frame is provided by the IDE and is used to control the size, location, docking state, and other persistent properties. The tool window pane displays the contents. The default size and location apply only when the tool window is first opened; after that the tool window state is persisted.  
  
 Tool window panes can host WPF user controls and support toolbars. You can override the <xref:Microsoft.VisualStudio.Shell.WindowPane.Window%2A> property to return the handle of the hosted control.  
  
 You can add many different features to tool windows. For example, you can add a toolbar: [Adding a Toolbar to a Tool Window](../extensibility/adding-a-toolbar-to-a-tool-window.md) or a shortcut menu: [Adding a Shortcut Menu in a Tool Window](../extensibility/adding-a-shortcut-menu-in-a-tool-window.md). You can add a Search control that allows you to search items inside your tool window: [Adding Search to a Tool Window](../extensibility/adding-search-to-a-tool-window.md).  
  
 You can subscribe to tool window events: [Subscribing to an Event](../extensibility/subscribing-to-an-event.md).  
  
## Extending Existing Tool Windows  
 You can add information about your tool window to a new **Options** page and a new setting on the **Properties** page, write to the **Task List** and **Output** windows. For more information, see [Extending the Properties, Task List, Output, and Options Windows](../extensibility/extending-the-properties-task-list-output-and-options-windows.md) and [Extending the Properties, Task List, Output, and Options Windows](../extensibility/extending-the-properties-task-list-output-and-options-windows.md).  
  
## Modal Dialog Boxes  
 In a Visual Studio extension you should create modal dialog boxes by deriving them from <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>, which allows you to control them and the rest of the UI. For more information, see . [Creating and Managing Modal Dialog Boxes](../extensibility/creating-and-managing-modal-dialog-boxes.md).  
  
## See Also  
 [Creating an Extension with a Tool Window](../extensibility/creating-an-extension-with-a-tool-window.md)