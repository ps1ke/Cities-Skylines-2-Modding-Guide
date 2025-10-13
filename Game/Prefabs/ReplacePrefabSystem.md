# Game.Prefabs.ReplacePrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ReplacePrefabSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.ReplacePrefabSystem+Finalize m_FinalizeSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PrefabRefQuery;
    private Unity.Entities.Entity m_OldPrefab;
    private Unity.Entities.Entity m_NewPrefab;
    private Unity.Entities.Entity m_SourceInstance;
    private Unity.Collections.NativeList<Game.Prefabs.ReplacePrefabSystem+ReplaceMesh> m_MeshReplaces;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdateInstances;
    private Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData> m_ReplacePrefabData;
    private Game.Prefabs.ReplacePrefabSystem+TypeHandle __TypeHandle;

    public ReplacePrefabSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CheckInstanceComponents(Unity.Entities.Entity instance, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> checkedComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> archetypeComponents);
    public System.Void FinalizeReplaces();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void ReplacePrefab(Unity.Entities.Entity oldPrefab, Unity.Entities.Entity newPrefab, Unity.Entities.Entity sourceInstance);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.ReplacePrefabSystem+Finalize m_FinalizeSystem`  

```csharp
private Game.Prefabs.ReplacePrefabSystem+Finalize m_FinalizeSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabRefQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabRefQuery;
```

- `private Unity.Entities.Entity m_OldPrefab`  

```csharp
private Unity.Entities.Entity m_OldPrefab;
```

- `private Unity.Entities.Entity m_NewPrefab`  

```csharp
private Unity.Entities.Entity m_NewPrefab;
```

- `private Unity.Entities.Entity m_SourceInstance`  

```csharp
private Unity.Entities.Entity m_SourceInstance;
```

- `private Unity.Collections.NativeList<Game.Prefabs.ReplacePrefabSystem+ReplaceMesh> m_MeshReplaces`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.ReplacePrefabSystem+ReplaceMesh> m_MeshReplaces;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdateInstances`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdateInstances;
```

- `private Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData> m_ReplacePrefabData`  

```csharp
private Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData> m_ReplacePrefabData;
```

- `private Game.Prefabs.ReplacePrefabSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ReplacePrefabSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ReplacePrefabSystem()`  

```csharp
[Preserve]
	public ReplacePrefabSystem()
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

- `private CheckInstanceComponents(Unity.Entities.Entity instance, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> checkedComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> archetypeComponents) : System.Void`  

```csharp
private void CheckInstanceComponents(Entity instance, HashSet<ComponentType> checkedComponents, HashSet<ComponentType> archetypeComponents)
	{
		NativeArray<ComponentType> componentTypes = base.EntityManager.GetChunk(instance).Archetype.GetComponentTypes();
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(instance);
		m_PrefabSystem.GetPrefab<PrefabBase>(componentData).GetArchetypeComponents(archetypeComponents);
		foreach (ComponentType item in componentTypes)
		{
			if (checkedComponents.Contains(item))
			{
				if (archetypeComponents.Contains(item))
				{
					archetypeComponents.Remove(item);
				}
				else
				{
					base.EntityManager.RemoveComponent(instance, item);
				}
			}
		}
		foreach (ComponentType archetypeComponent in archetypeComponents)
		{
			if (checkedComponents.Contains(archetypeComponent))
			{
				base.EntityManager.AddComponent(instance, archetypeComponent);
			}
		}
		archetypeComponents.Clear();
		componentTypes.Dispose();
	}
```

- `public FinalizeReplaces() : System.Void`  

```csharp
public void FinalizeReplaces()
	{
		m_FinalizeSystem.Update();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_FinalizeSystem = base.World.GetOrCreateSystemManaged<Finalize>();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
		m_ManagedBatchSystem = base.World.GetOrCreateSystemManaged<ManagedBatchSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabRefQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[13]
			{
				ComponentType.ReadWrite<PrefabRef>(),
				ComponentType.ReadWrite<SubObject>(),
				ComponentType.ReadWrite<SubNet>(),
				ComponentType.ReadWrite<SubArea>(),
				ComponentType.ReadWrite<PlaceholderObjectElement>(),
				ComponentType.ReadWrite<ServiceUpgradeBuilding>(),
				ComponentType.ReadWrite<BuildingUpgradeElement>(),
				ComponentType.ReadWrite<Effect>(),
				ComponentType.ReadWrite<ActivityLocationElement>(),
				ComponentType.ReadWrite<SubMesh>(),
				ComponentType.ReadWrite<LodMesh>(),
				ComponentType.ReadWrite<UIGroupElement>(),
				ComponentType.ReadWrite<TutorialPhaseRef>()
			}
		});
		m_MeshReplaces = new NativeList<ReplaceMesh>(1, Allocator.Persistent);
		m_UpdateInstances = new NativeQueue<Entity>(Allocator.Persistent);
		m_ReplacePrefabData = new NativeHashMap<Entity, ReplacePrefabData>(1, Allocator.Persistent);
		RequireForUpdate(m_PrefabRefQuery);
		base.Enabled = false;
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
		m_MeshReplaces.Dispose();
		m_UpdateInstances.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityCommandBuffer entityCommandBuffer = new EntityCommandBuffer(Allocator.TempJob, PlaybackPolicy.SinglePlayback);
		EntityCommandBuffer entityCommandBuffer2 = default(EntityCommandBuffer);
		m_ToolSystem.RequireFullUpdate();
		JobHandle jobHandle = default(JobHandle);
		if (base.EntityManager.HasComponent<MeshData>(m_OldPrefab))
		{
			entityCommandBuffer2 = new EntityCommandBuffer(Allocator.TempJob, PlaybackPolicy.SinglePlayback);
			JobHandle dependencies;
			JobHandle dependencies2;
			JobHandle dependencies3;
			RemoveBatchGroupsJob jobData = new RemoveBatchGroupsJob
			{
				m_OldMeshEntity = m_OldPrefab,
				m_NewMeshEntity = m_NewPrefab,
				m_MeshBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshBatch_RW_BufferLookup, ref base.CheckedStateRef),
				m_FadeBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_FadeBatch_RW_BufferLookup, ref base.CheckedStateRef),
				m_BatchGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_BatchGroup_RW_BufferLookup, ref base.CheckedStateRef),
				m_NativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: false, out dependencies),
				m_NativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: false, out dependencies2),
				m_NativeSubBatches = m_BatchManagerSystem.GetNativeSubBatches(readOnly: false, out dependencies3),
				m_EntityCommandBuffer = entityCommandBuffer2,
				m_ReplaceMeshes = m_MeshReplaces
			};
			jobHandle = JobHandle.CombineDependencies(jobHandle, IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, dependencies, dependencies2, dependencies3)));
			m_BatchManagerSystem.AddNativeBatchGroupsWriter(jobHandle);
			m_BatchManagerSystem.AddNativeBatchInstancesWriter(jobHandle);
			m_BatchManagerSystem.AddNativeSubBatchesWriter(jobHandle);
		}
		else
		{
			m_ReplacePrefabData[m_NewPrefab] = new ReplacePrefabData
			{
				m_OldPrefab = m_OldPrefab,
				m_SourceInstance = m_SourceInstance
			};
		}
		if (m_SourceInstance != Entity.Null)
		{
			m_UpdateInstances.Enqueue(m_SourceInstance);
		}
		ReplacePrefabJob jobData2 = new ReplacePrefabJob
		{
			m_OldPrefab = m_OldPrefab,
			m_NewPrefab = m_NewPrefab,
			m_SourceInstance = m_SourceInstance,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubObject_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubNetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubNet_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubAreaType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubArea_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PlaceholderObjectElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ServiceUpgradeBuildingType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeBuilding_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingUpgradeElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingUpgradeElement_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EffectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_Effect_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ActivityLocationElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubMeshType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubMesh_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_LodMeshType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_LodMesh_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_UIGroupElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_UIGroupElement_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_TutorialPhaseType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_TutorialPhaseRef_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_CommandBuffer = entityCommandBuffer.AsParallelWriter(),
			m_UpdateInstances = m_UpdateInstances.AsParallelWriter()
		};
		JobHandle.CombineDependencies(jobHandle, JobChunkExtensions.ScheduleParallel(jobData2, m_PrefabRefQuery, base.Dependency)).Complete();
		if (base.EntityManager.HasComponent<BuildingUpgradeElement>(m_OldPrefab))
		{
			DynamicBuffer<BuildingUpgradeElement> dynamicBuffer = base.EntityManager.AddBuffer<BuildingUpgradeElement>(m_NewPrefab);
			DynamicBuffer<BuildingUpgradeElement> buffer = base.EntityManager.GetBuffer<BuildingUpgradeElement>(m_OldPrefab, isReadOnly: true);
			dynamicBuffer.CopyFrom(buffer);
		}
		entityCommandBuffer.Playback(base.EntityManager);
		entityCommandBuffer.Dispose();
		if (entityCommandBuffer2.IsCreated)
		{
			entityCommandBuffer2.Playback(base.EntityManager);
			entityCommandBuffer2.Dispose();
		}
	}
```

- `public ReplacePrefab(Unity.Entities.Entity oldPrefab, Unity.Entities.Entity newPrefab, Unity.Entities.Entity sourceInstance) : System.Void`  

```csharp
public void ReplacePrefab(Entity oldPrefab, Entity newPrefab, Entity sourceInstance)
	{
		m_OldPrefab = oldPrefab;
		m_NewPrefab = newPrefab;
		m_SourceInstance = sourceInstance;
		try
		{
			base.Enabled = true;
			Update();
		}
		finally
		{
			base.Enabled = false;
		}
	}
```


## Nested types

- `Game.Prefabs.ReplacePrefabSystem+ReplaceMesh`  
- `Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData`  
- `Game.Prefabs.ReplacePrefabSystem+Finalize`  
- `Game.Prefabs.ReplacePrefabSystem+RemoveBatchGroupsJob`  
- `Game.Prefabs.ReplacePrefabSystem+ReplacePrefabJob`  
- `Game.Prefabs.ReplacePrefabSystem+TypeHandle`  

