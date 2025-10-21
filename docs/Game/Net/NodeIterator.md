# Game.Net.ConnectionWarningSystem+CollectOwnersJob2+NodeIterator

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct NodeIterator : Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>
{
    public Colossal.Mathematics.Bounds2 m_Bounds;
    public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData;
    public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_OwnerSet;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_Owners;

    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity entity);
}
```


## Fields

- `public Colossal.Mathematics.Bounds2 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds2 m_Bounds;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_OwnerSet`  

```csharp
public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_OwnerSet;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_Owners`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_Owners;
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


