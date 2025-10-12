# Game.Simulation.GraduationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public System.Int32 debugFastGraduationLevel`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Unity.Entities.EntityQuery m_StudentQuery`  
- `private Game.Simulation.GraduationSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1855827631_0`  
- `private Unity.Entities.EntityQuery __query_1855827631_1`  
- `public static const System.Int32 kUpdatesPerDay`  
- `public static const System.Int32 kCheckSlowdown`  

## Constructors

- `public GraduationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetDropoutProbability(Game.Citizens.Citizen citizen, System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData& economyParameters, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single efficiency, Game.Common.TimeData timeData) : System.Single`  
- `public static GetDropoutProbability(System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.Single age, System.Single studyWillingness, System.Int32 failedEducationCount, System.Single graduationProbability, Game.Prefabs.EconomyParameterData& economyParameters) : System.Single`  
- `public static GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single studyWillingness, System.Single efficiency) : System.Single`  
- `public static GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, System.Single graduationModifier, Unity.Mathematics.float2 collegeModifier, Unity.Mathematics.float2 uniModifier, System.Single studyWillingness, System.Single efficiency) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.GraduationSystem+GraduationJob`  
- `Game.Simulation.GraduationSystem+TypeHandle`  

