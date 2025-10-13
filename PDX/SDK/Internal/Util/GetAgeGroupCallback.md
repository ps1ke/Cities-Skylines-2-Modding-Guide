# PDX.SDK.Internal.Util.XboxUserHelper+GetAgeGroupCallback

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Util`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class GetAgeGroupCallback : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public GetAgeGroupCallback(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Int32 hResult, System.Nullable<Unity.XGamingRuntime.XUserAgeGroup> xUserAgeGroup, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.Int32 hResult, System.Nullable<Unity.XGamingRuntime.XUserAgeGroup> xUserAgeGroup);
}
```


## Constructors

- `public GetAgeGroupCallback(System.Object object, System.IntPtr method)`  

```csharp
public GetAgeGroupCallback(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Int32 hResult, System.Nullable<Unity.XGamingRuntime.XUserAgeGroup> xUserAgeGroup, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Int32 hResult, System.Nullable<Unity.XGamingRuntime.XUserAgeGroup> xUserAgeGroup, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.Int32 hResult, System.Nullable<Unity.XGamingRuntime.XUserAgeGroup> xUserAgeGroup) : System.Void`  

```csharp
public virtual System.Void Invoke(System.Int32 hResult, System.Nullable<Unity.XGamingRuntime.XUserAgeGroup> xUserAgeGroup);
```


