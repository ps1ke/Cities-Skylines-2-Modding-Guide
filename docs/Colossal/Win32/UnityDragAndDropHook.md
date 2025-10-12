# Colossal.Win32.UnityDragAndDropHook

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent OnDroppedFiles`  
- `private System.UInt32 threadId`  
- `private System.IntPtr mainWindow`  
- `private Colossal.Win32.HookProc m_Callback`  
- `private System.IntPtr m_Hook`  

## Constructors

- `public UnityDragAndDropHook()`  

## Methods

- `private Callback(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam) : System.IntPtr`  
- `public static GetMainWindow(System.UInt32 aThreadId, System.String aClassName = null) : System.IntPtr`  
- `public InstallHook() : System.Void`  
- `public UninstallHook() : System.Void`  

## Events

- `OnDroppedFiles` : `Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent`  

## Nested types

- `Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent`  
- `Colossal.Win32.UnityDragAndDropHook+<>c__DisplayClass9_0`  

