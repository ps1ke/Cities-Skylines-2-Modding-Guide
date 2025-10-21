# Game.Simulation.AircraftNavigationHelpers+AircraftCollisionIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct AircraftCollisionIterator : Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>
{
    public Unity.Entities.Entity m_Ignore;
    public Colossal.Mathematics.Line3+Segment m_Line;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.Entity m_Result;
    public System.Single m_ClosestT;

    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Entities.Entity m_Ignore`  

```csharp
public Unity.Entities.Entity m_Ignore;
```

- `public Colossal.Mathematics.Line3+Segment m_Line`  

```csharp
public Colossal.Mathematics.Line3+Segment m_Line;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.Entity m_Result`  

```csharp
public Unity.Entities.Entity m_Result;
```

- `public System.Single m_ClosestT`  

```csharp
public System.Single m_ClosestT;
```


## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  

```csharp
public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
```

- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity entity);
```


