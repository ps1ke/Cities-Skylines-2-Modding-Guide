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
public EventJournalSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetInfo(Unity.Entities.Entity journalEntity) : Game.Events.EventJournalEntry`  

```csharp
public Game.Events.EventJournalEntry GetInfo(Unity.Entities.Entity journalEntity);
```

- `public GetPrefab(Unity.Entities.Entity journalEntity) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity GetPrefab(Unity.Entities.Entity journalEntity);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  

```csharp
public System.Boolean TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data);
```

- `public TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  

```csharp
public System.Boolean TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data);
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

