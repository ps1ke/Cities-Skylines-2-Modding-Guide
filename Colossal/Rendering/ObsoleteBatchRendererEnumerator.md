# Colossal.Rendering.ObsoleteBatchRendererEnumerator

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ObsoleteBatchRendererEnumerator
{
    internal Unity.Collections.LowLevel.Unsafe.UnsafeList<UnityEngine.Rendering.BatchID> m_Enumerator;

    public System.Boolean GetNextObsoleteRenderer(UnityEngine.Rendering.BatchID& rendererIndex);
}
```


## Fields

- `internal Unity.Collections.LowLevel.Unsafe.UnsafeList<UnityEngine.Rendering.BatchID> m_Enumerator`  

```csharp
internal Unity.Collections.LowLevel.Unsafe.UnsafeList<UnityEngine.Rendering.BatchID> m_Enumerator;
```


## Methods

- `public GetNextObsoleteRenderer(UnityEngine.Rendering.BatchID& rendererIndex) : System.Boolean`  

```csharp
public System.Boolean GetNextObsoleteRenderer(UnityEngine.Rendering.BatchID& rendererIndex);
```


