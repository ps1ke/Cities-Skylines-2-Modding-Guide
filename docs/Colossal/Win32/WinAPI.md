# Colossal.Win32.WinAPI

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Int32 SM_CXCURSOR`  
- `public static const System.Int32 SM_CYCURSOR`  

## Methods

- `public static CallNextHookEx(System.IntPtr hhk, System.Int32 nCode, System.IntPtr wParam, Colossal.Win32.MSG& lParam) : System.IntPtr`  
- `public static DragAcceptFiles(System.IntPtr hwnd, System.Boolean fAccept) : System.Void`  
- `public static DragFinish(System.IntPtr hDrop) : System.Void`  
- `public static DragQueryFile(System.IntPtr hDrop, System.UInt32 iFile, System.Text.StringBuilder lpszFile, System.UInt32 cch) : System.UInt32`  
- `public static DragQueryPoint(System.IntPtr hDrop, Colossal.Win32.POINT& pos) : System.Void`  
- `public static GetCurrentThreadId() : System.UInt32`  
- `public static GetDpiForSystem() : System.Int32`  
- `public static GetModuleHandle(System.String lpModuleName) : System.IntPtr`  
- `public static GetSystemMetrics(System.Int32 nIndex) : System.Int32`  
- `public static SetWindowsHookEx(Colossal.Win32.HookType hookType, Colossal.Win32.HookProc lpfn, System.IntPtr hMod, System.UInt32 dwThreadId) : System.IntPtr`  
- `public static UnhookWindowsHookEx(System.IntPtr hhk) : System.Boolean`  

