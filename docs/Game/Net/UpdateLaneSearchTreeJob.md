# Game.Net.SearchSystem+UpdateLaneSearchTreeJob

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UpdateLaneSearchTreeJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Overridden> m_OverriddenType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.UtilityLane> m_UtilityLaneType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData;
    public System.Boolean m_EditorMode;
    public System.Boolean m_Loaded;
    public Game.Net.UtilityTypes m_DilatedUtilityTypes;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_SearchTree;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Overridden> m_OverriddenType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Overridden> m_OverriddenType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.UtilityLane> m_UtilityLaneType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.UtilityLane> m_UtilityLaneType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData;
```

- `public System.Boolean m_EditorMode`  

```csharp
public System.Boolean m_EditorMode;
```

- `public System.Boolean m_Loaded`  

```csharp
public System.Boolean m_Loaded;
```

- `public Game.Net.UtilityTypes m_DilatedUtilityTypes`  

```csharp
public Game.Net.UtilityTypes m_DilatedUtilityTypes;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```


## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


