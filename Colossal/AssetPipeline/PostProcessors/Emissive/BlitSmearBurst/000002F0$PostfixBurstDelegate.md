# Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitSmearBurst_000002F0$PostfixBurstDelegate

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class BlitSmearBurst_000002F0$PostfixBurstDelegate : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public BlitSmearBurst_000002F0$PostfixBurstDelegate(System.Object , System.IntPtr );

    public virtual System.IAsyncResult BeginInvoke(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.AsyncCallback , System.Object );
    public virtual System.Void EndInvoke(System.IAsyncResult );
    public virtual System.Void Invoke(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst);
}
```


## Constructors

- `public BlitSmearBurst_000002F0$PostfixBurstDelegate(System.Object , System.IntPtr )`  

```csharp
public BlitSmearBurst_000002F0$PostfixBurstDelegate(System.Object , System.IntPtr );
```


## Methods

- `public virtual BeginInvoke(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.AsyncCallback , System.Object ) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.AsyncCallback , System.Object );
```

- `public virtual EndInvoke(System.IAsyncResult ) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult );
```

- `public virtual Invoke(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst) : System.Void`  

```csharp
public virtual System.Void Invoke(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst);
```


