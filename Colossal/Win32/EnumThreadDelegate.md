# Colossal.Win32.EnumThreadDelegate

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class EnumThreadDelegate : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public EnumThreadDelegate(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.IntPtr Hwnd, System.IntPtr lParam, System.AsyncCallback callback, System.Object object);
    public virtual System.Boolean EndInvoke(System.IAsyncResult result);
    public virtual System.Boolean Invoke(System.IntPtr Hwnd, System.IntPtr lParam);
}
```


## Constructors

- `public EnumThreadDelegate(System.Object object, System.IntPtr method)`  

```csharp
public EnumThreadDelegate(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.IntPtr Hwnd, System.IntPtr lParam, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.IntPtr Hwnd, System.IntPtr lParam, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Boolean`  

```csharp
public virtual System.Boolean EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.IntPtr Hwnd, System.IntPtr lParam) : System.Boolean`  

```csharp
public virtual System.Boolean Invoke(System.IntPtr Hwnd, System.IntPtr lParam);
```


