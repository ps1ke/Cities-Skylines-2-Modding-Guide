# Game.Triggers.CreateChirpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_ChirpQuery`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> m_Queue`  
- `private Game.Triggers.CreateChirpSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CreateChirpSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Triggers.CreateChirpSystem+CollectRecentChirpsJob`  
- `Game.Triggers.CreateChirpSystem+CreateChirpJob`  
- `Game.Triggers.CreateChirpSystem+TypeHandle`  

