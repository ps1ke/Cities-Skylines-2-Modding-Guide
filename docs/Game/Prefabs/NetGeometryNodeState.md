# Game.Prefabs.NetGeometryNodeState

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetGeometryNodeState : Unity.Entities.IBufferElementData
{
    public Game.Prefabs.CompositionFlags m_CompositionAll;
    public Game.Prefabs.CompositionFlags m_CompositionAny;
    public Game.Prefabs.CompositionFlags m_CompositionNone;
    public Game.Prefabs.CompositionFlags m_State;
    public Game.Prefabs.NetEdgeMatchType m_MatchType;

}
```


## Fields

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

- `public Game.Prefabs.CompositionFlags m_State`  

```csharp
public Game.Prefabs.CompositionFlags m_State;
```

- `public Game.Prefabs.NetEdgeMatchType m_MatchType`  

```csharp
public Game.Prefabs.NetEdgeMatchType m_MatchType;
```


