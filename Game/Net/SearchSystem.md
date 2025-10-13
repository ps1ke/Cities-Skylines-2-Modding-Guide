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
[Preserve]
	public SearchSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public AddLaneSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddLaneSearchTreeReader(JobHandle jobHandle)
	{
		m_LaneReadDependencies = JobHandle.CombineDependencies(m_LaneReadDependencies, jobHandle);
	}
```

- `public AddLaneSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddLaneSearchTreeWriter(JobHandle jobHandle)
	{
		m_LaneWriteDependencies = jobHandle;
	}
```

- `public AddNetSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddNetSearchTreeReader(JobHandle jobHandle)
	{
		m_NetReadDependencies = JobHandle.CombineDependencies(m_NetReadDependencies, jobHandle);
	}
```

- `public AddNetSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddNetSearchTreeWriter(JobHandle jobHandle)
	{
		m_NetWriteDependencies = jobHandle;
	}
```

- `public GetLaneSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public NativeQuadTree<Entity, QuadTreeBoundsXZ> GetLaneSearchTree(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_LaneWriteDependencies : JobHandle.CombineDependencies(m_LaneReadDependencies, m_LaneWriteDependencies));
		return m_LaneSearchTree;
	}
```

- `public static GetLayers(Game.Common.Owner owner, Game.Net.UtilityLane utilityLane, Game.Prefabs.MeshLayer defaultLayers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas) : Game.Prefabs.MeshLayer`  

```csharp
public static MeshLayer GetLayers(Owner owner, UtilityLane utilityLane, MeshLayer defaultLayers, ref ComponentLookup<PrefabRef> prefabRefs, ref ComponentLookup<NetData> netDatas, ref ComponentLookup<NetGeometryData> netGeometryDatas)
	{
		if (defaultLayers == (MeshLayer.Pipeline | MeshLayer.SubPipeline))
		{
			if ((owner.m_Owner != Entity.Null && IsNetOwnerPipeline(owner, ref prefabRefs, ref netDatas, ref netGeometryDatas)) || (utilityLane.m_Flags & UtilityLaneFlags.PipelineConnection) != 0)
			{
				return MeshLayer.Pipeline;
			}
			return MeshLayer.SubPipeline;
		}
		return defaultLayers;
	}
```

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `public GetNetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public NativeQuadTree<Entity, QuadTreeBoundsXZ> GetNetSearchTree(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_NetWriteDependencies : JobHandle.CombineDependencies(m_NetReadDependencies, m_NetWriteDependencies));
		return m_NetSearchTree;
	}
```

- `public static IsNetOwnerPipeline(Game.Common.Owner owner, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas) : System.Boolean`  

```csharp
public static bool IsNetOwnerPipeline(Owner owner, ref ComponentLookup<PrefabRef> prefabRefs, ref ComponentLookup<NetData> netDatas, ref ComponentLookup<NetGeometryData> netGeometryDatas)
	{
		if (prefabRefs.TryGetComponent(owner.m_Owner, out var componentData) && netDatas.TryGetComponent(componentData.m_Prefab, out var componentData2) && netGeometryDatas.TryGetComponent(componentData.m_Prefab, out var componentData3))
		{
			if ((componentData2.m_RequiredLayers & (Layer.PowerlineLow | Layer.PowerlineHigh | Layer.WaterPipe | Layer.SewagePipe)) != Layer.None)
			{
				return (componentData3.m_Flags & GeometryFlags.Marker) == 0;
			}
			return false;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_UndergroundViewSystem = base.World.GetOrCreateSystemManaged<UndergroundViewSystem>();
		m_UpdatedNetsQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Edge>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Node>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UpdatedLanesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<LaneGeometry>(),
				ComponentType.ReadOnly<ParkingLane>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<LaneGeometry>(),
				ComponentType.ReadOnly<ParkingLane>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AllNetsQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Node>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AllLanesQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<LaneGeometry>(),
				ComponentType.ReadOnly<ParkingLane>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_NetSearchTree = new NativeQuadTree<Entity, QuadTreeBoundsXZ>(1f, Allocator.Persistent);
		m_LaneSearchTree = new NativeQuadTree<Entity, QuadTreeBoundsXZ>(1f, Allocator.Persistent);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_NetSearchTree.Dispose();
		m_LaneSearchTree.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery query = (loaded ? m_AllNetsQuery : m_UpdatedNetsQuery);
		EntityQuery query2 = (loaded ? m_AllLanesQuery : m_UpdatedLanesQuery);
		bool flag = !query.IsEmptyIgnoreFilter;
		bool flag2 = !query2.IsEmptyIgnoreFilter;
		if (flag || flag2)
		{
			JobHandle jobHandle = default(JobHandle);
			if (flag)
			{
				JobHandle dependencies;
				JobHandle jobHandle2 = JobChunkExtensions.Schedule(new UpdateNetSearchTreeJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_StartGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EndGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OrphanType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_MarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabCompositionMeshRef = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshRef_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabCompositionMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
					m_Loaded = loaded,
					m_SearchTree = GetNetSearchTree(readOnly: false, out dependencies)
				}, query, JobHandle.CombineDependencies(base.Dependency, dependencies));
				AddNetSearchTreeWriter(jobHandle2);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
			if (flag2)
			{
				JobHandle dependencies2;
				JobHandle jobHandle3 = JobChunkExtensions.Schedule(new UpdateLaneSearchTreeJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OverriddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_UtilityLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabLaneGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
					m_Loaded = loaded,
					m_DilatedUtilityTypes = m_UndergroundViewSystem.utilityTypes,
					m_SearchTree = GetLaneSearchTree(readOnly: false, out dependencies2)
				}, query2, JobHandle.CombineDependencies(base.Dependency, dependencies2));
				AddLaneSearchTreeWriter(jobHandle3);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
			}
			base.Dependency = jobHandle;
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		JobHandle dependencies;
		NativeQuadTree<Entity, QuadTreeBoundsXZ> netSearchTree = GetNetSearchTree(readOnly: false, out dependencies);
		JobHandle dependencies2;
		NativeQuadTree<Entity, QuadTreeBoundsXZ> laneSearchTree = GetLaneSearchTree(readOnly: false, out dependencies2);
		dependencies.Complete();
		dependencies2.Complete();
		netSearchTree.Clear();
		laneSearchTree.Clear();
		m_Loaded = true;
	}
```


## Nested types

- `Game.Net.SearchSystem+UpdateNetSearchTreeJob`  
- `Game.Net.SearchSystem+UpdateLaneSearchTreeJob`  
- `Game.Net.SearchSystem+TypeHandle`  

