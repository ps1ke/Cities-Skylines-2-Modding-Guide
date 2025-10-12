# Game.Simulation.CitizenBehaviorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Jobs.JobHandle m_CarReserveWriters`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_LeisureParameterQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Entities.EntityQuery m_PopulationQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityArchetype m_HouseholdArchetype`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_CarReserveQueue`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ParallelCarReserveQueue`  
- `private Game.Simulation.CitizenBehaviorSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Single kMaxPathfindCost`  
- `public static readonly System.Single kMaxMovingAwayCost`  
- `public static readonly System.Int32 kMinLeisurePossibility`  

## Constructors

- `public CitizenBehaviorSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddCarReserveWriter(Unity.Jobs.JobHandle writer) : System.Void`  
- `public GetCarReserveQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  
- `public static GetSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : Unity.Mathematics.float2`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static IsSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.Single normalizedTime, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CitizenBehaviorSystem+CitizenReserveHouseholdCarJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizenTryCollectMailJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizeSleepJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizenAITickJob`  
- `Game.Simulation.CitizenBehaviorSystem+TypeHandle`  

