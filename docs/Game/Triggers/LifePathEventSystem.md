# Game.Triggers.LifePathEventSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <m_DebugLifePathChirps>k__BackingField`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  
- `private Game.Triggers.CreateChirpSystem m_CreateChirpSystem`  
- `private Unity.Entities.EntityQuery m_FollowedQuery`  
- `private Unity.Entities.EntityQuery m_DeletedFollowedQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Entities.EntityArchetype m_EventArchetype`  
- `private Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> m_Queue`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Game.Triggers.LifePathEventSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kMaxFollowed`  

## Properties

- `public System.Boolean m_DebugLifePathChirps { get; set }`  

## Constructors

- `public LifePathEventSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public FollowCitizen(Unity.Entities.Entity citizen) : System.Boolean`  
- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public UnfollowCitizen(Unity.Entities.Entity citizen) : System.Boolean`  

## Nested types

- `Game.Triggers.LifePathEventSystem+CreateLifePathEventJob`  
- `Game.Triggers.LifePathEventSystem+CleanupLifePathEntriesJob`  
- `Game.Triggers.LifePathEventSystem+TypeHandle`  

