# Game.Simulation.StudentSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_GotoSchoolQuery`  
- `private Unity.Entities.EntityQuery m_StudentQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Entities.EntityQuery m_PopulationQuery`  
- `private Game.Simulation.StudentSystem+TypeHandle __TypeHandle`  

## Constructors

- `public StudentSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetStudyOffset(Game.Citizens.Citizen citizen) : System.Single`  
- `public static GetTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters) : Unity.Mathematics.float2`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static IsTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.StudentSystem+GoToSchoolJob`  
- `Game.Simulation.StudentSystem+StudyJob`  
- `Game.Simulation.StudentSystem+TypeHandle`  

