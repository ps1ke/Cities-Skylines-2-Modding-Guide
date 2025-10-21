# Game.Rendering.Emissive

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Emissive : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Collections.NativeHeapBlock m_BufferAllocation;
    public System.Int32 m_LightOffset;
    public System.Boolean m_Updated;

}
```


## Fields

- `public Colossal.Collections.NativeHeapBlock m_BufferAllocation`  

```csharp
public Colossal.Collections.NativeHeapBlock m_BufferAllocation;
```

- `public System.Int32 m_LightOffset`  

```csharp
public System.Int32 m_LightOffset;
```

- `public System.Boolean m_Updated`  

```csharp
public System.Boolean m_Updated;
```


