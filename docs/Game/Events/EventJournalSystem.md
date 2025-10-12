# Game.Events.EventJournalSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Events.IEventJournalSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_StartedJournalQuery`  
- `private Unity.Entities.EntityQuery m_DeletedEventQuery`  
- `private Unity.Entities.EntityQuery m_JournalDataEventQuery`  
- `private Unity.Entities.EntityQuery m_ActiveJournalEffectQuery`  
- `private Unity.Entities.EntityQuery m_JournalEventPrefabQuery`  
- `private Unity.Entities.EntityQuery m_LoadedJournalQuery`  
- `private Game.Simulation.ISimulationSystem m_SimulationSystem`  
- `private Game.Simulation.IBudgetSystem m_BudgetSystem`  
- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Started`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Changed`  
- `private Unity.Collections.NativeArray<System.Int32> m_CityEffects`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <eventJournal>k__BackingField`  
- `private System.Action<Unity.Entities.Entity> <eventEventDataChanged>k__BackingField`  
- `private System.Action <eventEntryAdded>k__BackingField`  
- `private Game.Events.EventJournalSystem+TypeHandle __TypeHandle`  

## Properties

- `public Unity.Collections.NativeList<Unity.Entities.Entity> eventJournal { get; private set }`  
- `public System.Action<Unity.Entities.Entity> eventEventDataChanged { get; set }`  
- `public System.Action eventEntryAdded { get; set }`  
- `public System.Collections.Generic.IEnumerable<Game.Prefabs.JournalEventComponent> eventPrefabs { get }`  

## Constructors

- `public EventJournalSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetInfo(Unity.Entities.Entity journalEntity) : Game.Events.EventJournalEntry`  
- `public GetPrefab(Unity.Entities.Entity journalEntity) : Unity.Entities.Entity`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  
- `public TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  

## Nested types

- `Game.Events.EventJournalSystem+StartedEventsJob`  
- `Game.Events.EventJournalSystem+DeletedEventsJob`  
- `Game.Events.EventJournalSystem+TrackCityEffectsJob`  
- `Game.Events.EventJournalSystem+TrackDataJob`  
- `Game.Events.EventJournalSystem+CheckJournalTrackingEndJob`  
- `Game.Events.EventJournalSystem+JournalSortingInfo`  
- `Game.Events.EventJournalSystem+TypeHandle`  
- `Game.Events.EventJournalSystem+<get_eventPrefabs>d__31`  

