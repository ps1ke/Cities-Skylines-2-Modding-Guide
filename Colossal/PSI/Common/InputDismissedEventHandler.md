# Colossal.PSI.Common.InputDismissedEventHandler

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class InputDismissedEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public InputDismissedEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.IVirtualKeyboardSupport keyboard, System.String text, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.PSI.Common.IVirtualKeyboardSupport keyboard, System.String text);
}
```


## Constructors

- `public InputDismissedEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public InputDismissedEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.IVirtualKeyboardSupport keyboard, System.String text, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.IVirtualKeyboardSupport keyboard, System.String text, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.PSI.Common.IVirtualKeyboardSupport keyboard, System.String text) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.PSI.Common.IVirtualKeyboardSupport keyboard, System.String text);
```


