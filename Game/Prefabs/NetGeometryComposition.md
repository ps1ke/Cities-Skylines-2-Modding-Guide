# Game.Prefabs.NetGeometryComposition

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetGeometryComposition : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Composition;
    public Game.Prefabs.CompositionFlags m_Mask;

}
```


## Fields

- `public Unity.Entities.Entity m_Composition`  

```csharp
public Unity.Entities.Entity m_Composition;
```

- `public Game.Prefabs.CompositionFlags m_Mask`  

```csharp
public Game.Prefabs.CompositionFlags m_Mask;
```


