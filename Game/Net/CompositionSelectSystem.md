# Game.Net.CompositionSelectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompositionSelectSystem : Game.GameSystemBase
{
    private Game.Prefabs.NetCompositionSystem m_NetCompositionSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Common.ModificationBarrier3 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private System.Boolean m_Loaded;
    private Game.Net.CompositionSelectSystem+TypeHandle __TypeHandle;

    public CompositionSelectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.NetCompositionSystem m_NetCompositionSystem`  

```csharp
private Game.Prefabs.NetCompositionSystem m_NetCompositionSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier3 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.CompositionSelectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.CompositionSelectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompositionSelectSystem()`  

```csharp
[Preserve]
	public CompositionSelectSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NetCompositionSystem = base.World.GetOrCreateSystemManaged<NetCompositionSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier3>();
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadWrite<Composition>(),
				ComponentType.ReadWrite<Orphan>()
			}
		});
		m_AllQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadWrite<Composition>(),
				ComponentType.ReadWrite<Orphan>()
			}
		});
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityQuery query = (GetLoaded() ? m_AllQuery : m_UpdatedQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			NativeQueue<CompositionCreateInfo> compositionCreateQueue = new NativeQueue<CompositionCreateInfo>(Allocator.TempJob);
			SelectCompositionJob jobData = new SelectCompositionJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UpgradedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FixedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OrphanType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Orphan_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FixedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabPlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabGeometryCompositions = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryComposition_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabGeometryEdgeStates = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryEdgeState_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabGeometryNodeStates = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryNodeState_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabFixedNetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_FixedNetElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
				m_CompositionCreateQueue = compositionCreateQueue.AsParallelWriter()
			};
			CreateCompositionJob jobData2 = new CreateCompositionJob
			{
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTerrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetTerrainData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubReplacements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabGeometrySections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetGeometrySection_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubSections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetSubSection_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSectionPieces = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetSectionPiece_RO_BufferLookup, ref base.CheckedStateRef),
				m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RW_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RW_ComponentLookup, ref base.CheckedStateRef),
				m_CompositionCreateQueue = compositionCreateQueue,
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
			};
			JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(jobData, query, base.Dependency);
			JobHandle jobHandle = IJobExtensions.Schedule(jobData2, dependsOn);
			compositionCreateQueue.Dispose(jobHandle);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Net.CompositionSelectSystem+CompositionCreateInfo`  
- `Game.Net.CompositionSelectSystem+SelectCompositionJob`  
- `Game.Net.CompositionSelectSystem+CreatedCompositionKey`  
- `Game.Net.CompositionSelectSystem+CreateCompositionJob`  
- `Game.Net.CompositionSelectSystem+TypeHandle`  

