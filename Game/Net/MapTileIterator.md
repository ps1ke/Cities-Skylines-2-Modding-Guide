# Game.Net.ConnectionWarningSystem+CheckOwnersJob+MapTileIterator

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct MapTileIterator : Colossal.Collections.INativeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>
{
    public System.Int32 m_Result;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Entities.ComponentLookup<Game.Common.Native> m_NativeData;
    public Unity.Entities.ComponentLookup<Game.Areas.MapTile> m_MapTileData;
    public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
    public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles;

    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem item);
}
```


## Fields

- `public System.Int32 m_Result`  

```csharp
public System.Int32 m_Result;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Native> m_NativeData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Native> m_NativeData;
```

- `public Unity.Entities.ComponentLookup<Game.Areas.MapTile> m_MapTileData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Areas.MapTile> m_MapTileData;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles;
```


## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  

```csharp
public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
```

- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem item) : System.Void`  

```csharp
public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem item);
```


