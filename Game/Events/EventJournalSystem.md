# Game.Events.EventJournalSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Events.IEventJournalSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventJournalSystem : Game.GameSystemBase, Game.Events.IEventJournalSystem
{
    private Unity.Entities.EntityQuery m_StartedJournalQuery;
    private Unity.Entities.EntityQuery m_DeletedEventQuery;
    private Unity.Entities.EntityQuery m_JournalDataEventQuery;
    private Unity.Entities.EntityQuery m_ActiveJournalEffectQuery;
    private Unity.Entities.EntityQuery m_JournalEventPrefabQuery;
    private Unity.Entities.EntityQuery m_LoadedJournalQuery;
    private Game.Simulation.ISimulationSystem m_SimulationSystem;
    private Game.Simulation.IBudgetSystem m_BudgetSystem;
    private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Started;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Changed;
    private Unity.Collections.NativeArray<System.Int32> m_CityEffects;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <eventJournal>k__BackingField;
    private System.Action<Unity.Entities.Entity> <eventEventDataChanged>k__BackingField;
    private System.Action <eventEntryAdded>k__BackingField;
    private Game.Events.EventJournalSystem+TypeHandle __TypeHandle;

    public Unity.Collections.NativeList<Unity.Entities.Entity> eventJournal { get; private set; }
    public System.Action<Unity.Entities.Entity> eventEventDataChanged { get; set; }
    public System.Action eventEntryAdded { get; set; }
    public System.Collections.Generic.IEnumerable<Game.Prefabs.JournalEventComponent> eventPrefabs { get; }

    public EventJournalSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Events.EventJournalEntry GetInfo(Unity.Entities.Entity journalEntity);
    public Unity.Entities.Entity GetPrefab(Unity.Entities.Entity journalEntity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Boolean TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data);
    public System.Boolean TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_StartedJournalQuery`  

```csharp
private Unity.Entities.EntityQuery m_StartedJournalQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedEventQuery;
```

- `private Unity.Entities.EntityQuery m_JournalDataEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_JournalDataEventQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveJournalEffectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveJournalEffectQuery;
```

- `private Unity.Entities.EntityQuery m_JournalEventPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_JournalEventPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_LoadedJournalQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedJournalQuery;
```

- `private Game.Simulation.ISimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.ISimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.IBudgetSystem m_BudgetSystem`  

```csharp
private Game.Simulation.IBudgetSystem m_BudgetSystem;
```

- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  

```csharp
private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Started`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Started;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Changed`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Changed;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CityEffects`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CityEffects;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <eventJournal>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <eventJournal>k__BackingField;
```

- `private System.Action<Unity.Entities.Entity> <eventEventDataChanged>k__BackingField`  

```csharp
private System.Action<Unity.Entities.Entity> <eventEventDataChanged>k__BackingField;
```

- `private System.Action <eventEntryAdded>k__BackingField`  

```csharp
private System.Action <eventEntryAdded>k__BackingField;
```

- `private Game.Events.EventJournalSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.EventJournalSystem+TypeHandle __TypeHandle;
```


## Properties

- `public Unity.Collections.NativeList<Unity.Entities.Entity> eventJournal { get; private set }`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> eventJournal { get; private set; }
```

- `public System.Action<Unity.Entities.Entity> eventEventDataChanged { get; set }`  

```csharp
public System.Action<Unity.Entities.Entity> eventEventDataChanged { get; set; }
```

- `public System.Action eventEntryAdded { get; set }`  

```csharp
public System.Action eventEntryAdded { get; set; }
```

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.JournalEventComponent> eventPrefabs { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.JournalEventComponent> eventPrefabs { get; }
```


## Constructors

- `public EventJournalSystem()`  

```csharp
[Preserve]
	public EventJournalSystem()
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

- `public GetInfo(Unity.Entities.Entity journalEntity) : Game.Events.EventJournalEntry`  

```csharp
public EventJournalEntry GetInfo(Entity journalEntity)
	{
		return base.EntityManager.GetComponentData<EventJournalEntry>(journalEntity);
	}
```

- `public GetPrefab(Unity.Entities.Entity journalEntity) : Unity.Entities.Entity`  

```csharp
public Entity GetPrefab(Entity journalEntity)
	{
		return base.EntityManager.GetComponentData<PrefabRef>(journalEntity).m_Prefab;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_StartedJournalQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadWrite<EventJournalEntry>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<EventJournalPending>()
			}
		});
		m_DeletedEventQuery = GetEntityQuery(ComponentType.ReadOnly<JournalEvent>(), ComponentType.ReadOnly<Deleted>());
		m_ActiveJournalEffectQuery = GetEntityQuery(ComponentType.ReadWrite<EventJournalCityEffect>(), ComponentType.Exclude<EventJournalPending>(), ComponentType.Exclude<EventJournalCompleted>());
		m_JournalDataEventQuery = GetEntityQuery(ComponentType.ReadOnly<AddEventJournalData>(), ComponentType.ReadOnly<Game.Common.Event>());
		m_JournalEventPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<EventPrefab>(), ComponentType.ReadOnly<PrefabData>());
		m_LoadedJournalQuery = GetEntityQuery(ComponentType.ReadOnly<EventJournalEntry>(), ComponentType.Exclude<EventJournalPending>());
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_BudgetSystem = base.World.GetOrCreateSystemManaged<BudgetSystem>();
		m_CityServiceBudgetSystem = base.World.GetOrCreateSystemManaged<CityServiceBudgetSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		eventJournal = new NativeList<Entity>(Allocator.Persistent);
		m_Started = new NativeQueue<Entity>(Allocator.Persistent);
		m_Changed = new NativeQueue<Entity>(Allocator.Persistent);
		m_CityEffects = new NativeArray<int>(5, Allocator.Persistent);
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
		eventJournal.Dispose();
		m_Changed.Dispose();
		m_Started.Dispose();
		m_CityEffects.Dispose();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		eventJournal.Clear();
		m_Changed.Clear();
		m_Started.Clear();
		if (!m_LoadedJournalQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = m_LoadedJournalQuery.ToEntityArray(Allocator.TempJob);
			NativeArray<EventJournalEntry> nativeArray2 = m_LoadedJournalQuery.ToComponentDataArray<EventJournalEntry>(Allocator.TempJob);
			NativeArray<JournalSortingInfo> array = new NativeArray<JournalSortingInfo>(nativeArray.Length, Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				array[i] = new JournalSortingInfo
				{
					m_Entity = nativeArray[i],
					m_StartFrame = nativeArray2[i].m_StartFrame
				};
			}
			nativeArray.Dispose();
			nativeArray2.Dispose();
			array.Sort();
			for (int j = 0; j < array.Length; j++)
			{
				NativeList<Entity> nativeList = eventJournal;
				JournalSortingInfo journalSortingInfo = array[j];
				nativeList.Add(in journalSortingInfo.m_Entity);
			}
			array.Dispose();
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = false;
		Entity item;
		while (m_Started.TryDequeue(out item))
		{
			eventJournal.Add(in item);
			flag = true;
		}
		if (flag)
		{
			eventEntryAdded?.Invoke();
		}
		Entity item2;
		while (m_Changed.TryDequeue(out item2))
		{
			eventEventDataChanged?.Invoke(item2);
		}
		if ((!m_StartedJournalQuery.IsEmptyIgnoreFilter || !m_ActiveJournalEffectQuery.IsEmptyIgnoreFilter) && base.EntityManager.TryGetComponent<Population>(m_CitySystem.City, out var component) && base.EntityManager.TryGetComponent<Tourism>(m_CitySystem.City, out var component2))
		{
			m_CityEffects[0] = 0;
			m_CityEffects[1] = component.m_AverageHappiness;
			m_CityEffects[2] = m_CityServiceBudgetSystem.GetTotalTaxIncome();
			m_CityEffects[3] = m_BudgetSystem.GetTotalTradeWorth();
			m_CityEffects[4] = component2.m_CurrentTourists;
		}
		if (!m_StartedJournalQuery.IsEmptyIgnoreFilter)
		{
			StartedEventsJob jobData = new StartedEventsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PendingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_EventJournalPending_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CityEffectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Events_EventJournalCityEffect_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_EntryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_EventJournalEntry_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SimulationFrame = m_SimulationSystem.frameIndex,
				m_CityEffects = m_CityEffects,
				m_Started = m_Started.AsParallelWriter(),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_StartedJournalQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		}
		if (!m_DeletedEventQuery.IsEmptyIgnoreFilter)
		{
			DeletedEventsJob jobData2 = new DeletedEventsJob
			{
				m_JournalEventType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_JournalEvent_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CompletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_EventJournalCompleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EntryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_EventJournalEntry_RW_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_DeletedEventQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		}
		if (!m_ActiveJournalEffectQuery.IsEmptyIgnoreFilter)
		{
			CheckJournalTrackingEndJob jobData3 = new CheckJournalTrackingEndJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_EntryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_EventJournalEntry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_Fire_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TargetElementData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_TargetElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_OnFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData3, m_ActiveJournalEffectQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
			TrackCityEffectsJob jobData4 = new TrackCityEffectsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CityEffectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Events_EventJournalCityEffect_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_CityEffects = m_CityEffects,
				m_Changes = m_Changed.AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData4, m_ActiveJournalEffectQuery, base.Dependency);
		}
		if (!m_JournalDataEventQuery.IsEmptyIgnoreFilter)
		{
			TrackDataJob jobData5 = new TrackDataJob
			{
				m_AddDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_AddEventJournalData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_JournalEvents = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_JournalEvent_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EventJournalDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_EventJournalData_RW_BufferLookup, ref base.CheckedStateRef),
				m_Changes = m_Changed
			};
			base.Dependency = JobChunkExtensions.Schedule(jobData5, m_JournalDataEventQuery, base.Dependency);
		}
	}
```

- `public TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  

```csharp
public bool TryGetCityEffects(Entity journalEntity, out DynamicBuffer<EventJournalCityEffect> data)
	{
		if (base.EntityManager.HasComponent<EventJournalCityEffect>(journalEntity))
		{
			data = base.EntityManager.GetBuffer<EventJournalCityEffect>(journalEntity, isReadOnly: true);
			return true;
		}
		data = default(DynamicBuffer<EventJournalCityEffect>);
		return false;
	}
```

- `public TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  

```csharp
public bool TryGetData(Entity journalEntity, out DynamicBuffer<EventJournalData> data)
	{
		if (base.EntityManager.HasComponent<EventJournalData>(journalEntity))
		{
			data = base.EntityManager.GetBuffer<EventJournalData>(journalEntity, isReadOnly: true);
			return true;
		}
		data = default(DynamicBuffer<EventJournalData>);
		return false;
	}
```


## Nested types

- `Game.Events.EventJournalSystem+StartedEventsJob`  
- `Game.Events.EventJournalSystem+DeletedEventsJob`  
- `Game.Events.EventJournalSystem+TrackCityEffectsJob`  
- `Game.Events.EventJournalSystem+TrackDataJob`  
- `Game.Events.EventJournalSystem+CheckJournalTrackingEndJob`  
- `Game.Events.EventJournalSystem+JournalSortingInfo`  
- `Game.Events.EventJournalSystem+TypeHandle`  
- `Game.Events.EventJournalSystem+<get_eventPrefabs>d__31`  

