# Colossal.PSI.Common.ModEventHandler

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class ModEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public ModEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod);
}
```


## Constructors

- `public ModEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public ModEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod);
```


