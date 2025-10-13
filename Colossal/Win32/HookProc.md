# Colossal.Win32.HookProc

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class HookProc : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public HookProc(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam, System.AsyncCallback callback, System.Object object);
    public virtual System.IntPtr EndInvoke(Colossal.Win32.MSG& lParam, System.IAsyncResult result);
    public virtual System.IntPtr Invoke(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam);
}
```


## Constructors

- `public HookProc(System.Object object, System.IntPtr method)`  

```csharp
public HookProc(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(Colossal.Win32.MSG& lParam, System.IAsyncResult result) : System.IntPtr`  

```csharp
public virtual System.IntPtr EndInvoke(Colossal.Win32.MSG& lParam, System.IAsyncResult result);
```

- `public virtual Invoke(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam) : System.IntPtr`  

```csharp
public virtual System.IntPtr Invoke(System.Int32 code, System.IntPtr wParam, Colossal.Win32.MSG& lParam);
```


