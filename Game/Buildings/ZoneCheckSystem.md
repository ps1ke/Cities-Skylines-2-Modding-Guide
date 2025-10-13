# Game.Buildings.ZoneCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneCheckSystem : Game.GameSystemBase
{
    private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Game.Buildings.ZoneCheckSystem+TypeHandle __TypeHandle;

    public ZoneCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem`  

```csharp
private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Game.Buildings.ZoneCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ZoneCheckSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZoneCheckSystem()`  

```csharp
[Preserve]
	public ZoneCheckSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ZoneUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Zones.UpdateCollectSystem>();
		m_ZoneSearchSystem = base.World.GetOrCreateSystemManaged<Game.Zones.SearchSystem>();
		m_ModificationEndBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_BuildingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ZoneUpdateCollectSystem.isUpdated && !m_BuildingSettingsQuery.IsEmptyIgnoreFilter)
		{
			NativeQueue<Entity> queue = new NativeQueue<Entity>(Allocator.TempJob);
			NativeList<Entity> list = new NativeList<Entity>(Allocator.TempJob);
			JobHandle dependencies;
			NativeList<Bounds2> updatedBounds = m_ZoneUpdateCollectSystem.GetUpdatedBounds(readOnly: true, out dependencies);
			JobHandle dependencies2;
			FindSpawnableBuildingsJob jobData = new FindSpawnableBuildingsJob
			{
				m_Bounds = updatedBounds.AsDeferredJobArray(),
				m_SearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies2),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSignatureBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResultQueue = queue.AsParallelWriter()
			};
			CollectEntitiesJob jobData2 = new CollectEntitiesJob
			{
				m_Queue = queue,
				m_List = list
			};
			JobHandle dependencies3;
			CheckBuildingZonesJob jobData3 = new CheckBuildingZonesJob
			{
				m_CondemnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Condemned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ValidAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_ValidArea_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AbandonedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabPlaceholderBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RO_BufferLookup, ref base.CheckedStateRef),
				m_BuildingConfigurationData = m_BuildingSettingsQuery.GetSingleton<BuildingConfigurationData>(),
				m_Buildings = list.AsDeferredJobArray(),
				m_SearchTree = m_ZoneSearchSystem.GetSearchTree(readOnly: true, out dependencies3),
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
				m_CommandBuffer = m_ModificationEndBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			JobHandle jobHandle = jobData.Schedule(updatedBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
			JobHandle jobHandle3 = jobData3.Schedule(list, 1, JobHandle.CombineDependencies(jobHandle2, dependencies3));
			queue.Dispose(jobHandle2);
			list.Dispose(jobHandle3);
			m_ZoneUpdateCollectSystem.AddBoundsReader(jobHandle);
			m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
			m_ZoneSearchSystem.AddSearchTreeReader(jobHandle3);
			m_IconCommandSystem.AddCommandBufferWriter(jobHandle3);
			m_ModificationEndBarrier.AddJobHandleForProducer(jobHandle3);
			base.Dependency = jobHandle3;
		}
	}
```


## Nested types

- `Game.Buildings.ZoneCheckSystem+FindSpawnableBuildingsJob`  
- `Game.Buildings.ZoneCheckSystem+CollectEntitiesJob`  
- `Game.Buildings.ZoneCheckSystem+CheckBuildingZonesJob`  
- `Game.Buildings.ZoneCheckSystem+TypeHandle`  

