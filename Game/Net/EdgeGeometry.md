# Game.Net.EdgeGeometry

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct EdgeGeometry : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Game.Net.Segment m_Start;
    public Game.Net.Segment m_End;
    public Colossal.Mathematics.Bounds3 m_Bounds;

}
```


## Fields

- `public Game.Net.Segment m_Start`  

```csharp
public Game.Net.Segment m_Start;
```

- `public Game.Net.Segment m_End`  

```csharp
public Game.Net.Segment m_End;
```

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```


