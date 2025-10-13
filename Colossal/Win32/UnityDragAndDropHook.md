# Colossal.Win32.UnityDragAndDropHook

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class UnityDragAndDropHook
{
    private Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent OnDroppedFiles;
    private System.UInt32 threadId;
    private System.IntPtr mainWindow;
    private Colossal.Win32.HookProc m_Callback;
    private System.IntPtr m_Hook;

    public UnityDragAndDropHook();

    private System.IntPtr Callback(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam);
    public static System.IntPtr GetMainWindow(System.UInt32 aThreadId, System.String aClassName);
    public System.Void InstallHook();
    public System.Void UninstallHook();
}
```


## Fields

- `private Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent OnDroppedFiles`  

```csharp
private Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent OnDroppedFiles;
```

- `private System.UInt32 threadId`  

```csharp
private System.UInt32 threadId;
```

- `private System.IntPtr mainWindow`  

```csharp
private System.IntPtr mainWindow;
```

- `private Colossal.Win32.HookProc m_Callback`  

```csharp
private Colossal.Win32.HookProc m_Callback;
```

- `private System.IntPtr m_Hook`  

```csharp
private System.IntPtr m_Hook;
```


## Constructors

- `public UnityDragAndDropHook()`  

```csharp
public UnityDragAndDropHook();
```


## Methods

- `private Callback(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam) : System.IntPtr`  

```csharp
private System.IntPtr Callback(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam);
```

- `public static GetMainWindow(System.UInt32 aThreadId, System.String aClassName = null) : System.IntPtr`  

```csharp
public static System.IntPtr GetMainWindow(System.UInt32 aThreadId, System.String aClassName);
```

- `public InstallHook() : System.Void`  

```csharp
public System.Void InstallHook();
```

- `public UninstallHook() : System.Void`  

```csharp
public System.Void UninstallHook();
```


## Events

- `OnDroppedFiles` : `Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent`  

```csharp
public event Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent OnDroppedFiles;
```


## Nested types

- `Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent`  
- `Colossal.Win32.UnityDragAndDropHook+<>c__DisplayClass9_0`  

