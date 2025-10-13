# Game.Notifications.IconCommandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IconCommandSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command>> m_Queues;
    private Unity.Jobs.JobHandle m_Dependencies;
    private System.Int32 m_BufferIndex;
    private Game.Notifications.IconCommandSystem+TypeHandle __TypeHandle;

    public IconCommandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddCommandBufferWriter(Unity.Jobs.JobHandle handle);
    public Game.Notifications.IconCommandBuffer CreateCommandBuffer();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command>> m_Queues`  

```csharp
private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command>> m_Queues;
```

- `private Unity.Jobs.JobHandle m_Dependencies`  

```csharp
private Unity.Jobs.JobHandle m_Dependencies;
```

- `private System.Int32 m_BufferIndex`  

```csharp
private System.Int32 m_BufferIndex;
```

- `private Game.Notifications.IconCommandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Notifications.IconCommandSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IconCommandSystem()`  

```csharp
[Preserve]
	public IconCommandSystem()
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

- `public AddCommandBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddCommandBufferWriter(JobHandle handle)
	{
		m_Dependencies = JobHandle.CombineDependencies(m_Dependencies, handle);
	}
```

- `public CreateCommandBuffer() : Game.Notifications.IconCommandBuffer`  

```csharp
public IconCommandBuffer CreateCommandBuffer()
	{
		NativeQueue<IconCommandBuffer.Command> item = new NativeQueue<IconCommandBuffer.Command>(Allocator.TempJob);
		m_Queues.Add(item);
		return new IconCommandBuffer(item.AsParallelWriter(), m_BufferIndex++);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_Queues = new List<NativeQueue<IconCommandBuffer.Command>>();
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<IconConfigurationData>());
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		m_Dependencies.Complete();
		for (int i = 0; i < m_Queues.Count; i++)
		{
			m_Queues[i].Dispose();
		}
		m_Queues.Clear();
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_Dependencies.Complete();
		m_BufferIndex = 0;
		int num = 0;
		for (int i = 0; i < m_Queues.Count; i++)
		{
			num += m_Queues[i].Count;
		}
		if (num == 0 || m_ConfigurationQuery.IsEmptyIgnoreFilter)
		{
			for (int j = 0; j < m_Queues.Count; j++)
			{
				m_Queues[j].Dispose();
			}
			m_Queues.Clear();
			return;
		}
		NativeArray<IconCommandBuffer.Command> commands = new NativeArray<IconCommandBuffer.Command>(num, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
		num = 0;
		for (int k = 0; k < m_Queues.Count; k++)
		{
			NativeQueue<IconCommandBuffer.Command> nativeQueue = m_Queues[k];
			int count = nativeQueue.Count;
			for (int l = 0; l < count; l++)
			{
				commands[num++] = nativeQueue.Dequeue();
			}
			nativeQueue.Dispose();
		}
		m_Queues.Clear();
		JobHandle jobHandle = IJobExtensions.Schedule(new IconCommandPlaybackJob
		{
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NotificationIconData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NotificationIconData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_IconAnimations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_IconAnimationElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_IconData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RW_ComponentLookup, ref base.CheckedStateRef),
			m_IconElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Notifications_IconElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_ConfigurationEntity = m_ConfigurationQuery.GetSingletonEntity(),
			m_DeltaTime = UnityEngine.Time.deltaTime,
			m_Commands = commands,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Notifications.IconCommandSystem+IconCommandPlaybackJob`  
- `Game.Notifications.IconCommandSystem+TypeHandle`  

