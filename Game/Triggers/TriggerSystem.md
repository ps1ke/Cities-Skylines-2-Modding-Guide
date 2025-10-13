# Game.Triggers.TriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TriggerSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.TriggerPrefabSystem m_TriggerPrefabSystem;
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>> m_Queues;
    private Unity.Jobs.JobHandle m_Dependencies;
    private Game.Triggers.CreateChirpSystem m_CreateChirpSystem;
    private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
    private Game.Triggers.RadioTagSystem m_RadioTagSystem;
    private Game.Tutorials.TutorialEventActivationSystem m_TutorialEventActivationSystem;
    private System.DateTime m_LastTimedEventTime;
    private System.TimeSpan m_TimedEventInterval;
    private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_TriggerFrames;
    private Game.Triggers.TriggerSystem+TypeHandle __TypeHandle;

    public TriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddActionBufferWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> CreateActionBuffer();
    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.TriggerPrefabSystem m_TriggerPrefabSystem`  

```csharp
private Game.Prefabs.TriggerPrefabSystem m_TriggerPrefabSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>> m_Queues`  

```csharp
private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>> m_Queues;
```

- `private Unity.Jobs.JobHandle m_Dependencies`  

```csharp
private Unity.Jobs.JobHandle m_Dependencies;
```

- `private Game.Triggers.CreateChirpSystem m_CreateChirpSystem`  

```csharp
private Game.Triggers.CreateChirpSystem m_CreateChirpSystem;
```

- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  

```csharp
private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
```

- `private Game.Triggers.RadioTagSystem m_RadioTagSystem`  

```csharp
private Game.Triggers.RadioTagSystem m_RadioTagSystem;
```

- `private Game.Tutorials.TutorialEventActivationSystem m_TutorialEventActivationSystem`  

```csharp
private Game.Tutorials.TutorialEventActivationSystem m_TutorialEventActivationSystem;
```

- `private System.DateTime m_LastTimedEventTime`  

```csharp
private System.DateTime m_LastTimedEventTime;
```

- `private System.TimeSpan m_TimedEventInterval`  

```csharp
private System.TimeSpan m_TimedEventInterval;
```

- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_TriggerFrames`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_TriggerFrames;
```

- `private Game.Triggers.TriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.TriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TriggerSystem()`  

```csharp
[Preserve]
	public TriggerSystem()
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

- `public AddActionBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddActionBufferWriter(JobHandle handle)
	{
		m_Dependencies = JobHandle.CombineDependencies(m_Dependencies, handle);
	}
```

- `public CreateActionBuffer() : Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>`  

```csharp
public NativeQueue<TriggerAction> CreateActionBuffer()
	{
		Assert.IsTrue(base.Enabled, "Can not write to queue when system isn't running");
		NativeQueue<TriggerAction> nativeQueue = new NativeQueue<TriggerAction>(Allocator.TempJob);
		m_Queues.Add(nativeQueue);
		return nativeQueue;
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TriggerPrefabSystem = base.World.GetOrCreateSystemManaged<TriggerPrefabSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_CreateChirpSystem = base.World.GetOrCreateSystemManaged<CreateChirpSystem>();
		m_LifePathEventSystem = base.World.GetOrCreateSystemManaged<LifePathEventSystem>();
		m_RadioTagSystem = base.World.GetOrCreateSystemManaged<RadioTagSystem>();
		m_TutorialEventActivationSystem = base.World.GetOrCreateSystemManaged<TutorialEventActivationSystem>();
		m_Queues = new List<NativeQueue<TriggerAction>>();
		m_LastTimedEventTime = DateTime.MinValue;
		m_TimedEventInterval = new TimeSpan(0, 15, 0);
		m_TriggerFrames = new NativeParallelHashMap<Entity, uint>(32, Allocator.Persistent);
		m_EDWSBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.EarlyDisasterWarningSystem>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
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
		base.OnDestroy();
		m_TriggerFrames.Dispose();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
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
		base.Dependency.Complete();
		m_Dependencies.Complete();
		int num = 0;
		for (int i = 0; i < m_Queues.Count; i++)
		{
			num += m_Queues[i].Count;
		}
		if (num == 0)
		{
			for (int j = 0; j < m_Queues.Count; j++)
			{
				m_Queues[j].Dispose();
			}
			m_Queues.Clear();
		}
		NativeArray<TriggerAction> actions = new NativeArray<TriggerAction>(num, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
		num = 0;
		for (int k = 0; k < m_Queues.Count; k++)
		{
			NativeQueue<TriggerAction> nativeQueue = m_Queues[k];
			int count = nativeQueue.Count;
			for (int l = 0; l < count; l++)
			{
				actions[num++] = nativeQueue.Dequeue();
			}
			nativeQueue.Dispose();
		}
		m_Queues.Clear();
		JobHandle dependencies;
		JobHandle deps;
		JobHandle deps2;
		JobHandle deps3;
		JobHandle deps4;
		JobHandle dependency;
		TriggerActionJob jobData = new TriggerActionJob
		{
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_RandomSeed = RandomSeed.Next(),
			m_TriggerPrefabData = m_TriggerPrefabSystem.ReadTriggerPrefabData(out dependencies),
			m_Actions = actions,
			m_ChirpQueue = m_CreateChirpSystem.GetQueue(out deps),
			m_TriggerFrames = m_TriggerFrames,
			m_LifePathEventQueue = m_LifePathEventSystem.GetQueue(out deps2),
			m_RadioTagQueue = m_RadioTagSystem.GetInputQueue(out deps3),
			m_EmergencyRadioTagQueue = m_RadioTagSystem.GetEmergencyInputQueue(out deps4),
			m_TutorialTriggerQueue = m_TutorialEventActivationSystem.GetQueue(out dependency),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ChirpData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_TriggerChirpData_RO_BufferLookup, ref base.CheckedStateRef),
			m_LifePathEventData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LifePathEventData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RadioEventData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RadioEventData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TutorialEventData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_TutorialActivationEventData_RO_BufferLookup, ref base.CheckedStateRef),
			m_CitizenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PolicyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PolicyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TriggerConditions = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_TriggerConditionData_RO_BufferLookup, ref base.CheckedStateRef),
			m_CullingInfo = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficAccidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrafficAccidentData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TriggerLimitData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TriggerLimitData_RO_ComponentLookup, ref base.CheckedStateRef)
		};
		Camera main = Camera.main;
		if (main != null)
		{
			jobData.m_CameraPosition = main.transform.position;
		}
		JobHandle jobHandle = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, dependencies, deps2, deps, deps3, deps4, dependency));
		m_CreateChirpSystem.AddQueueWriter(jobHandle);
		m_LifePathEventSystem.AddQueueWriter(jobHandle);
		m_RadioTagSystem.AddInputQueueWriter(jobHandle);
		m_RadioTagSystem.AddEmergencyInputQueueWriter(jobHandle);
		m_TriggerPrefabSystem.AddReader(jobHandle);
		m_TutorialEventActivationSystem.AddQueueWriter(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
		if (DateTime.Now - m_LastTimedEventTime >= m_TimedEventInterval)
		{
			Telemetry.CityStats();
			m_LastTimedEventTime = DateTime.Now;
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_TriggerFrames.Clear();
	}
```


## Nested types

- `Game.Triggers.TriggerSystem+TriggerActionJob`  
- `Game.Triggers.TriggerSystem+TypeHandle`  

