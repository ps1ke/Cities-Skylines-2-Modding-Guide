# Colossal.Win32.WinAPI

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class WinAPI
{
    public static const System.Int32 SM_CXCURSOR;
    public static const System.Int32 SM_CYCURSOR;

    public static System.IntPtr CallNextHookEx(System.IntPtr hhk, System.Int32 nCode, System.IntPtr wParam, Colossal.Win32.MSG& lParam);
    public static System.Void DragAcceptFiles(System.IntPtr hwnd, System.Boolean fAccept);
    public static System.Void DragFinish(System.IntPtr hDrop);
    public static System.UInt32 DragQueryFile(System.IntPtr hDrop, System.UInt32 iFile, System.Text.StringBuilder lpszFile, System.UInt32 cch);
    public static System.Void DragQueryPoint(System.IntPtr hDrop, Colossal.Win32.POINT& pos);
    public static System.UInt32 GetCurrentThreadId();
    public static System.Int32 GetDpiForSystem();
    public static System.IntPtr GetModuleHandle(System.String lpModuleName);
    public static System.Int32 GetSystemMetrics(System.Int32 nIndex);
    public static System.IntPtr SetWindowsHookEx(Colossal.Win32.HookType hookType, Colossal.Win32.HookProc lpfn, System.IntPtr hMod, System.UInt32 dwThreadId);
    public static System.Boolean UnhookWindowsHookEx(System.IntPtr hhk);
}
```


## Fields

- `public static const System.Int32 SM_CXCURSOR`  

```csharp
public static const System.Int32 SM_CXCURSOR;
```

- `public static const System.Int32 SM_CYCURSOR`  

```csharp
public static const System.Int32 SM_CYCURSOR;
```


## Methods

- `public static CallNextHookEx(System.IntPtr hhk, System.Int32 nCode, System.IntPtr wParam, Colossal.Win32.MSG& lParam) : System.IntPtr`  

```csharp
public static System.IntPtr CallNextHookEx(System.IntPtr hhk, System.Int32 nCode, System.IntPtr wParam, Colossal.Win32.MSG& lParam);
```

- `public static DragAcceptFiles(System.IntPtr hwnd, System.Boolean fAccept) : System.Void`  

```csharp
public static System.Void DragAcceptFiles(System.IntPtr hwnd, System.Boolean fAccept);
```

- `public static DragFinish(System.IntPtr hDrop) : System.Void`  

```csharp
public static System.Void DragFinish(System.IntPtr hDrop);
```

- `public static DragQueryFile(System.IntPtr hDrop, System.UInt32 iFile, System.Text.StringBuilder lpszFile, System.UInt32 cch) : System.UInt32`  

```csharp
public static System.UInt32 DragQueryFile(System.IntPtr hDrop, System.UInt32 iFile, System.Text.StringBuilder lpszFile, System.UInt32 cch);
```

- `public static DragQueryPoint(System.IntPtr hDrop, Colossal.Win32.POINT& pos) : System.Void`  

```csharp
public static System.Void DragQueryPoint(System.IntPtr hDrop, Colossal.Win32.POINT& pos);
```

- `public static GetCurrentThreadId() : System.UInt32`  

```csharp
public static System.UInt32 GetCurrentThreadId();
```

- `public static GetDpiForSystem() : System.Int32`  

```csharp
public static System.Int32 GetDpiForSystem();
```

- `public static GetModuleHandle(System.String lpModuleName) : System.IntPtr`  

```csharp
public static System.IntPtr GetModuleHandle(System.String lpModuleName);
```

- `public static GetSystemMetrics(System.Int32 nIndex) : System.Int32`  

```csharp
public static System.Int32 GetSystemMetrics(System.Int32 nIndex);
```

- `public static SetWindowsHookEx(Colossal.Win32.HookType hookType, Colossal.Win32.HookProc lpfn, System.IntPtr hMod, System.UInt32 dwThreadId) : System.IntPtr`  

```csharp
public static System.IntPtr SetWindowsHookEx(Colossal.Win32.HookType hookType, Colossal.Win32.HookProc lpfn, System.IntPtr hMod, System.UInt32 dwThreadId);
```

- `public static UnhookWindowsHookEx(System.IntPtr hhk) : System.Boolean`  

```csharp
public static System.Boolean UnhookWindowsHookEx(System.IntPtr hhk);
```


