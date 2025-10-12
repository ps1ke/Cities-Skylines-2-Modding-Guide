# Colossal.Win32.EnumThreadDelegate

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public EnumThreadDelegate(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(System.IntPtr Hwnd, System.IntPtr lParam, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Boolean`  
- `public virtual Invoke(System.IntPtr Hwnd, System.IntPtr lParam) : System.Boolean`  

