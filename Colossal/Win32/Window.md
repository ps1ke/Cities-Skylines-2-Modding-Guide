# Colossal.Win32.Window

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class Window
{
    public static System.Boolean EnumThreadWindows(System.UInt32 dwThreadId, Colossal.Win32.EnumThreadDelegate lpfn, System.IntPtr lParam);
    private static System.Int32 GetClassName(System.IntPtr hWnd, System.Text.StringBuilder lpClassName, System.Int32 nMaxCount);
    public static System.String GetClassName(System.IntPtr hWnd);
    public static System.Boolean GetWindowRect(System.IntPtr hwnd, Colossal.Win32.RECT& lpRect);
    private static System.Int32 GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount);
    public static System.String GetWindowText(System.IntPtr hWnd);
    private static System.Int32 GetWindowTextLength(System.IntPtr hWnd);
    public static System.Boolean IsWindowVisible(System.IntPtr hWnd);
}
```


## Methods

- `public static EnumThreadWindows(System.UInt32 dwThreadId, Colossal.Win32.EnumThreadDelegate lpfn, System.IntPtr lParam) : System.Boolean`  

```csharp
public static System.Boolean EnumThreadWindows(System.UInt32 dwThreadId, Colossal.Win32.EnumThreadDelegate lpfn, System.IntPtr lParam);
```

- `private static GetClassName(System.IntPtr hWnd, System.Text.StringBuilder lpClassName, System.Int32 nMaxCount) : System.Int32`  

```csharp
private static System.Int32 GetClassName(System.IntPtr hWnd, System.Text.StringBuilder lpClassName, System.Int32 nMaxCount);
```

- `public static GetClassName(System.IntPtr hWnd) : System.String`  

```csharp
public static System.String GetClassName(System.IntPtr hWnd);
```

- `public static GetWindowRect(System.IntPtr hwnd, Colossal.Win32.RECT& lpRect) : System.Boolean`  

```csharp
public static System.Boolean GetWindowRect(System.IntPtr hwnd, Colossal.Win32.RECT& lpRect);
```

- `private static GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount) : System.Int32`  

```csharp
private static System.Int32 GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount);
```

- `public static GetWindowText(System.IntPtr hWnd) : System.String`  

```csharp
public static System.String GetWindowText(System.IntPtr hWnd);
```

- `private static GetWindowTextLength(System.IntPtr hWnd) : System.Int32`  

```csharp
private static System.Int32 GetWindowTextLength(System.IntPtr hWnd);
```

- `public static IsWindowVisible(System.IntPtr hWnd) : System.Boolean`  

```csharp
public static System.Boolean IsWindowVisible(System.IntPtr hWnd);
```


