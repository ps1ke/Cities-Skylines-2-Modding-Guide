# Colossal.Rendering.UpdatedPropertiesEnumerator

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct UpdatedPropertiesEnumerator
{
    internal Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashSet<System.Int32> m_Enumerator;

    public System.Boolean GetNextUpdatedGroup(System.Int32& groupIndex);
}
```


## Fields

- `internal Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashSet<System.Int32> m_Enumerator`  

```csharp
internal Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashSet<System.Int32> m_Enumerator;
```


## Methods

- `public GetNextUpdatedGroup(System.Int32& groupIndex) : System.Boolean`  

```csharp
public System.Boolean GetNextUpdatedGroup(System.Int32& groupIndex);
```


