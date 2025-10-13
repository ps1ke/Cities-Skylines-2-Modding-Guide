# Game.Simulation.CommonPathfindSetup+TargetIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct TargetIterator : Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>
{
    public Unity.Entities.Entity m_Entity;
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public Unity.Mathematics.float3 m_Position;
    public System.Single m_MaxDistance;
    public Game.Pathfind.PathfindTargetSeeker<Game.Simulation.PathfindSetupBuffer> m_TargetSeeker;
    public Game.Pathfind.EdgeFlags m_Flags;
    public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;

    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity);
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public System.Single m_MaxDistance`  

```csharp
public System.Single m_MaxDistance;
```

- `public Game.Pathfind.PathfindTargetSeeker<Game.Simulation.PathfindSetupBuffer> m_TargetSeeker`  

```csharp
public Game.Pathfind.PathfindTargetSeeker<Game.Simulation.PathfindSetupBuffer> m_TargetSeeker;
```

- `public Game.Pathfind.EdgeFlags m_Flags`  

```csharp
public Game.Pathfind.EdgeFlags m_Flags;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
```


## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  

```csharp
public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
```

- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity) : System.Void`  

```csharp
public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity);
```


