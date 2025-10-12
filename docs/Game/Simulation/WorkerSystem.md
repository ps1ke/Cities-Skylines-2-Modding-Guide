# Game.Simulation.WorkerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_GotoWorkQuery`  
- `private Unity.Entities.EntityQuery m_WorkerQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Entities.EntityQuery m_PopulationQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.WorkerSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WorkerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Boolean includeCommute) : Unity.Mathematics.float2`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static GetWorkOffset(Game.Citizens.Citizen citizen) : System.Single`  
- `public static IsTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay) : System.Boolean`  
- `public static IsTodayOffDay(Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WorkerSystem+GoToWorkJob`  
- `Game.Simulation.WorkerSystem+WorkJob`  
- `Game.Simulation.WorkerSystem+TypeHandle`  

