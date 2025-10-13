# Colossal.PSI.PdxSdk.OnAccountLinkChangeEventHandler

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnAccountLinkChangeEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnAccountLinkChangeEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider);
}
```


## Constructors

- `public OnAccountLinkChangeEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public OnAccountLinkChangeEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider);
```


