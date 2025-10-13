# Game.Areas.Batch

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct Batch : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Collections.NativeHeapBlock m_BatchAllocation;
    public System.Int32 m_AllocatedSize;
    public System.Int32 m_BatchIndex;
    public System.Int32 m_VisibleCount;
    public System.Int32 m_MetaIndex;

}
```


## Fields

- `public Colossal.Collections.NativeHeapBlock m_BatchAllocation`  

```csharp
public Colossal.Collections.NativeHeapBlock m_BatchAllocation;
```

- `public System.Int32 m_AllocatedSize`  

```csharp
public System.Int32 m_AllocatedSize;
```

- `public System.Int32 m_BatchIndex`  

```csharp
public System.Int32 m_BatchIndex;
```

- `public System.Int32 m_VisibleCount`  

```csharp
public System.Int32 m_VisibleCount;
```

- `public System.Int32 m_MetaIndex`  

```csharp
public System.Int32 m_MetaIndex;
```


