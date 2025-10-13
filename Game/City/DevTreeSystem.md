# Game.City.DevTreeSystem

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DevTreeSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_MilestoneReachedQuery;
    private Unity.Entities.EntityQuery m_DevTreePointsQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.City.DevTreeSystem+TypeHandle __TypeHandle;

    public System.Int32 points { get; set; }

    public DevTreeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Boolean CheckRequirements(Unity.Entities.DynamicBuffer<Game.Prefabs.DevTreeNodeRequirement> requirements, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked);
    private static System.Boolean CheckService(Unity.Entities.Entity service, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void Purchase(Game.Prefabs.DevTreeNodePrefab nodePrefab);
    public System.Void Purchase(Unity.Entities.Entity node);
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_MilestoneReachedQuery`  

```csharp
private Unity.Entities.EntityQuery m_MilestoneReachedQuery;
```

- `private Unity.Entities.EntityQuery m_DevTreePointsQuery`  

```csharp
private Unity.Entities.EntityQuery m_DevTreePointsQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.City.DevTreeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.City.DevTreeSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 points { get; set }`  

```csharp
public System.Int32 points { get; set; }
```


## Constructors

- `public DevTreeSystem()`  

```csharp
[Preserve]
	public DevTreeSystem()
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

- `private static CheckRequirements(Unity.Entities.DynamicBuffer<Game.Prefabs.DevTreeNodeRequirement> requirements, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked) : System.Boolean`  

```csharp
private static bool CheckRequirements(DynamicBuffer<DevTreeNodeRequirement> requirements, ComponentLookup<Locked> locked)
	{
		bool flag = false;
		for (int i = 0; i < requirements.Length; i++)
		{
			if (requirements[i].m_Node != Entity.Null)
			{
				flag = true;
				if (!locked.HasEnabledComponent(requirements[i].m_Node))
				{
					return true;
				}
			}
		}
		return !flag;
	}
```

- `private static CheckService(Unity.Entities.Entity service, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked) : System.Boolean`  

```csharp
private static bool CheckService(Entity service, ComponentLookup<Locked> locked)
	{
		if (!(service == Entity.Null))
		{
			return !locked.HasEnabledComponent(service);
		}
		return true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_MilestoneReachedQuery = GetEntityQuery(ComponentType.ReadOnly<MilestoneReachedEvent>());
		m_DevTreePointsQuery = GetEntityQuery(ComponentType.ReadWrite<DevTreePoints>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Unlock>(), ComponentType.ReadWrite<Event>());
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		RequireForUpdate(m_DevTreePointsQuery);
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
		if (!m_MilestoneReachedQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			AppendPointsJob jobData = new AppendPointsJob
			{
				m_Chunks = m_DevTreePointsQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_MilestoneReached = m_MilestoneReachedQuery.ToComponentDataListAsync<MilestoneReachedEvent>(Allocator.TempJob, out outJobHandle2),
				m_Milestones = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MilestoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PointsType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_City_DevTreePoints_RW_ComponentTypeHandle, ref base.CheckedStateRef)
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle, outJobHandle2));
			jobData.m_Chunks.Dispose(base.Dependency);
			jobData.m_MilestoneReached.Dispose(base.Dependency);
		}
	}
```

- `public Purchase(Game.Prefabs.DevTreeNodePrefab nodePrefab) : System.Void`  

```csharp
public void Purchase(Entity node)
	{
		if (!m_DevTreePointsQuery.IsEmptyIgnoreFilter)
		{
			ComponentLookup<DevTreeNodeData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DevTreeNodeData_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Locked> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef);
			DevTreeNodeData devTreeNodeData = componentLookup[node];
			int num = points;
			if (devTreeNodeData.m_Cost <= num && componentLookup2.HasEnabledComponent(node) && CheckService(devTreeNodeData.m_Service, componentLookup2) && (!base.EntityManager.HasComponent<DevTreeNodeRequirement>(node) || CheckRequirements(base.EntityManager.GetBuffer<DevTreeNodeRequirement>(node, isReadOnly: true), componentLookup2)))
			{
				num -= devTreeNodeData.m_Cost;
				points = num;
				EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
				Entity e = entityCommandBuffer.CreateEntity(m_UnlockEventArchetype);
				entityCommandBuffer.SetComponent(e, new Unlock(node));
				Telemetry.DevNodePurchased(m_PrefabSystem.GetPrefab<DevTreeNodePrefab>(node));
			}
		}
	}
```

- `public Purchase(Unity.Entities.Entity node) : System.Void`  

```csharp
public void Purchase(Entity node)
	{
		if (!m_DevTreePointsQuery.IsEmptyIgnoreFilter)
		{
			ComponentLookup<DevTreeNodeData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DevTreeNodeData_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Locked> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef);
			DevTreeNodeData devTreeNodeData = componentLookup[node];
			int num = points;
			if (devTreeNodeData.m_Cost <= num && componentLookup2.HasEnabledComponent(node) && CheckService(devTreeNodeData.m_Service, componentLookup2) && (!base.EntityManager.HasComponent<DevTreeNodeRequirement>(node) || CheckRequirements(base.EntityManager.GetBuffer<DevTreeNodeRequirement>(node, isReadOnly: true), componentLookup2)))
			{
				num -= devTreeNodeData.m_Cost;
				points = num;
				EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
				Entity e = entityCommandBuffer.CreateEntity(m_UnlockEventArchetype);
				entityCommandBuffer.SetComponent(e, new Unlock(node));
				Telemetry.DevNodePurchased(m_PrefabSystem.GetPrefab<DevTreeNodePrefab>(node));
			}
		}
	}
```


## Nested types

- `Game.City.DevTreeSystem+AppendPointsJob`  
- `Game.City.DevTreeSystem+TypeHandle`  

