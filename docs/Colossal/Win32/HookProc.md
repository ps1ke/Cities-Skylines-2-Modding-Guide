# Colossal.Win32.HookProc

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public HookProc(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(Colossal.Win32.MSG& lParam, System.IAsyncResult result) : System.IntPtr`  
- `public virtual Invoke(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam) : System.IntPtr`  

