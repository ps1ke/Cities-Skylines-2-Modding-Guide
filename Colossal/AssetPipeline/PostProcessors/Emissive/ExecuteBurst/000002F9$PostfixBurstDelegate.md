# Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader+ExecuteBurst_000002F9$PostfixBurstDelegate

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class ExecuteBurst_000002F9$PostfixBurstDelegate : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public ExecuteBurst_000002F9$PostfixBurstDelegate(System.Object , System.IntPtr );

    public virtual System.IAsyncResult BeginInvoke(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2, System.AsyncCallback , System.Object );
    public virtual System.Void EndInvoke(System.IAsyncResult );
    public virtual System.Void Invoke(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
}
```


## Constructors

- `public ExecuteBurst_000002F9$PostfixBurstDelegate(System.Object , System.IntPtr )`  

```csharp
public ExecuteBurst_000002F9$PostfixBurstDelegate(System.Object , System.IntPtr );
```


## Methods

- `public virtual BeginInvoke(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2, System.AsyncCallback , System.Object ) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2, System.AsyncCallback , System.Object );
```

- `public virtual EndInvoke(System.IAsyncResult ) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult );
```

- `public virtual Invoke(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
```


