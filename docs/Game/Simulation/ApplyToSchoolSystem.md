# Game.Simulation.ApplyToSchoolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public System.Boolean debugFastApplySchool`  
- `private Unity.Entities.EntityQuery m_CitizenGroup`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.ApplyToSchoolSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_2069025490_0`  
- `private Unity.Entities.EntityQuery __query_2069025490_1`  
- `private Unity.Entities.EntityQuery __query_2069025490_2`  
- `public static readonly System.Int32 kCoolDown`  
- `public static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public ApplyToSchoolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetEnteringProbability(Game.Citizens.CitizenAge age, System.Boolean worker, System.Int32 level, System.Int32 wellbeing, System.Single willingness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.EducationParameterData& educationParameterData) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ApplyToSchoolSystem+ApplyToSchoolJob`  
- `Game.Simulation.ApplyToSchoolSystem+TypeHandle`  

