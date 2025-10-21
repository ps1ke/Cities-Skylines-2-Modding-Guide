# Game.Rendering.Skeleton

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Skeleton : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Collections.NativeHeapBlock m_BufferAllocation;
    public System.Int32 m_BoneOffset;
    public System.Boolean m_CurrentUpdated;
    public System.Boolean m_HistoryUpdated;
    public System.Boolean m_RequireHistory;

}
```


## Fields

- `public Colossal.Collections.NativeHeapBlock m_BufferAllocation`  

```csharp
public Colossal.Collections.NativeHeapBlock m_BufferAllocation;
```

- `public System.Int32 m_BoneOffset`  

```csharp
public System.Int32 m_BoneOffset;
```

- `public System.Boolean m_CurrentUpdated`  

```csharp
public System.Boolean m_CurrentUpdated;
```

- `public System.Boolean m_HistoryUpdated`  

```csharp
public System.Boolean m_HistoryUpdated;
```

- `public System.Boolean m_RequireHistory`  

```csharp
public System.Boolean m_RequireHistory;
```


