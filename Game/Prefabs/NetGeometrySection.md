# Game.Prefabs.NetGeometrySection

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetGeometrySection : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Section;
    public Game.Prefabs.CompositionFlags m_CompositionAll;
    public Game.Prefabs.CompositionFlags m_CompositionAny;
    public Game.Prefabs.CompositionFlags m_CompositionNone;
    public Game.Prefabs.NetSectionFlags m_Flags;
    public Unity.Mathematics.float3 m_Offset;

}
```


## Fields

- `public Unity.Entities.Entity m_Section`  

```csharp
public Unity.Entities.Entity m_Section;
```

- `public Game.Prefabs.CompositionFlags m_CompositionAll`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionAll;
```

- `public Game.Prefabs.CompositionFlags m_CompositionAny`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionAny;
```

- `public Game.Prefabs.CompositionFlags m_CompositionNone`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionNone;
```

- `public Game.Prefabs.NetSectionFlags m_Flags`  

```csharp
public Game.Prefabs.NetSectionFlags m_Flags;
```

- `public Unity.Mathematics.float3 m_Offset`  

```csharp
public Unity.Mathematics.float3 m_Offset;
```


