# Colossal.Rendering.ObsoleteManagedBatchEnumerator

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ObsoleteManagedBatchEnumerator
{
    internal Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32> m_Enumerator;

    public System.Boolean GetNextObsoleteBatch(System.Int32& managedBatchIndex);
}
```


## Fields

- `internal Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32> m_Enumerator`  

```csharp
internal Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32> m_Enumerator;
```


## Methods

- `public GetNextObsoleteBatch(System.Int32& managedBatchIndex) : System.Boolean`  

```csharp
public System.Boolean GetNextObsoleteBatch(System.Int32& managedBatchIndex);
```


