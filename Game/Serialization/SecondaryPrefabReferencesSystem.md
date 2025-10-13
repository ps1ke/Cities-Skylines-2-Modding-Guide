# Game.Serialization.SecondaryPrefabReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SecondaryPrefabReferencesSystem : Game.GameSystemBase
{
    private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
    private Unity.Entities.EntityQuery m_SpawnableBuildingQuery;
    private Unity.Entities.EntityQuery m_PlaceholderBuildingQuery;
    private Unity.Entities.EntityQuery m_ServiceObjectQuery;
    private Unity.Entities.EntityQuery m_NetLaneQuery;
    private Unity.Entities.EntityQuery m_TransportLineQuery;
    private Unity.Entities.EntityQuery m_ContentPrerequisiteQuery;
    private Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle __TypeHandle;

    public SecondaryPrefabReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  

```csharp
private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
```

- `private Unity.Entities.EntityQuery m_SpawnableBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_PlaceholderBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlaceholderBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceObjectQuery;
```

- `private Unity.Entities.EntityQuery m_NetLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetLaneQuery;
```

- `private Unity.Entities.EntityQuery m_TransportLineQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportLineQuery;
```

- `private Unity.Entities.EntityQuery m_ContentPrerequisiteQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContentPrerequisiteQuery;
```

- `private Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SecondaryPrefabReferencesSystem()`  

```csharp
[Preserve]
	public SecondaryPrefabReferencesSystem()
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
		m_CheckPrefabReferencesSystem = base.World.GetOrCreateSystemManaged<CheckPrefabReferencesSystem>();
		m_SpawnableBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<SpawnableBuildingData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Deleted>());
		m_PlaceholderBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<PlaceholderBuildingData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Deleted>());
		m_ServiceObjectQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceObjectData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Deleted>());
		m_NetLaneQuery = GetEntityQuery(ComponentType.ReadOnly<NetLaneData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Deleted>());
		m_TransportLineQuery = GetEntityQuery(ComponentType.ReadOnly<TransportLineData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Deleted>());
		m_ContentPrerequisiteQuery = GetEntityQuery(ComponentType.ReadOnly<ContentPrerequisiteData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Deleted>());
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
		JobHandle dependencies;
		PrefabReferences prefabReferences = m_CheckPrefabReferencesSystem.GetPrefabReferences(this, out dependencies);
		dependencies = JobHandle.CombineDependencies(base.Dependency, dependencies);
		FixSpawnableBuildingJob jobData = new FixSpawnableBuildingJob
		{
			m_SpawnableBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = prefabReferences
		};
		FixPlaceholderBuildingJob jobData2 = new FixPlaceholderBuildingJob
		{
			m_PlaceholderBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceholderBuildingData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = prefabReferences
		};
		FixServiceObjectDataJob jobData3 = new FixServiceObjectDataJob
		{
			m_ServiceObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = prefabReferences
		};
		FixNetLaneDataJob jobData4 = new FixNetLaneDataJob
		{
			m_NetLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = prefabReferences
		};
		FixTransportLineDataJob jobData5 = new FixTransportLineDataJob
		{
			m_TransportLineType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TransportLineData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = prefabReferences
		};
		FixContentPrerequisiteDataJob jobData6 = new FixContentPrerequisiteDataJob
		{
			m_ContentPrerequisiteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ContentPrerequisiteData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = prefabReferences
		};
		JobHandle job = JobChunkExtensions.ScheduleParallel(jobData, m_SpawnableBuildingQuery, dependencies);
		JobHandle job2 = JobChunkExtensions.ScheduleParallel(jobData2, m_PlaceholderBuildingQuery, dependencies);
		JobHandle job3 = JobChunkExtensions.ScheduleParallel(jobData3, m_ServiceObjectQuery, dependencies);
		JobHandle job4 = JobChunkExtensions.ScheduleParallel(jobData4, m_NetLaneQuery, dependencies);
		JobHandle job5 = JobChunkExtensions.ScheduleParallel(jobData5, m_TransportLineQuery, dependencies);
		JobHandle job6 = JobChunkExtensions.ScheduleParallel(jobData6, m_ContentPrerequisiteQuery, dependencies);
		dependencies = JobUtils.CombineDependencies(job, job2, job3, job4, job5, job6);
		m_CheckPrefabReferencesSystem.AddPrefabReferencesUser(dependencies);
		base.Dependency = dependencies;
	}
```


## Nested types

- `Game.Serialization.SecondaryPrefabReferencesSystem+FixSpawnableBuildingJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixPlaceholderBuildingJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixServiceObjectDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixNetLaneDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixTransportLineDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixContentPrerequisiteDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle`  

