# Game.Net.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Unity.Entities.EntityQuery m_UpdatedNetsQuery;
    private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
    private Unity.Entities.EntityQuery m_AllNetsQuery;
    private Unity.Entities.EntityQuery m_AllLanesQuery;
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_NetSearchTree;
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_LaneSearchTree;
    private Unity.Jobs.JobHandle m_NetReadDependencies;
    private Unity.Jobs.JobHandle m_NetWriteDependencies;
    private Unity.Jobs.JobHandle m_LaneReadDependencies;
    private Unity.Jobs.JobHandle m_LaneWriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Net.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddLaneSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddLaneSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddNetSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddNetSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetLaneSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public static Game.Prefabs.MeshLayer GetLayers(Game.Common.Owner owner, Game.Net.UtilityLane utilityLane, Game.Prefabs.MeshLayer defaultLayers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetNetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public static System.Boolean IsNetOwnerPipeline(Game.Common.Owner owner, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedNetsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedNetsQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_AllNetsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllNetsQuery;
```

- `private Unity.Entities.EntityQuery m_AllLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllLanesQuery;
```

- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_NetSearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_NetSearchTree;
```

- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_LaneSearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_LaneSearchTree;
```

- `private Unity.Jobs.JobHandle m_NetReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NetReadDependencies;
```

- `private Unity.Jobs.JobHandle m_NetWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NetWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_LaneReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_LaneReadDependencies;
```

- `private Unity.Jobs.JobHandle m_LaneWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_LaneWriteDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.SearchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SearchSystem()`  

```csharp
public SearchSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddLaneSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddLaneSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddLaneSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddLaneSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public AddNetSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddNetSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddNetSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddNetSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public GetLaneSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetLaneSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `public static GetLayers(Game.Common.Owner owner, Game.Net.UtilityLane utilityLane, Game.Prefabs.MeshLayer defaultLayers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas) : Game.Prefabs.MeshLayer`  

```csharp
public static Game.Prefabs.MeshLayer GetLayers(Game.Common.Owner owner, Game.Net.UtilityLane utilityLane, Game.Prefabs.MeshLayer defaultLayers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetNetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetNetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `public static IsNetOwnerPipeline(Game.Common.Owner owner, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas) : System.Boolean`  

```csharp
public static System.Boolean IsNetOwnerPipeline(Game.Common.Owner owner, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Net.SearchSystem+UpdateNetSearchTreeJob`  
- `Game.Net.SearchSystem+UpdateLaneSearchTreeJob`  
- `Game.Net.SearchSystem+TypeHandle`  

