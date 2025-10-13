# Colossal.PSI.PdxSdk.OnLoggedInEventHandler

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnLoggedInEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnLoggedInEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime);
}
```


## Constructors

- `public OnLoggedInEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public OnLoggedInEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime) : System.Void`  

```csharp
public virtual System.Void Invoke(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime);
```


