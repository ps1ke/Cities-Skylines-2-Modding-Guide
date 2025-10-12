# Game.Simulation.CountHouseholdDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Entities.EntityQuery m_RequirementQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private Unity.Jobs.JobHandle m_HouseholdDataWriteDependencies`  
- `private Unity.Jobs.JobHandle m_HouseholdDataReadDependencies`  
- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdData> m_HouseholdCountData`  
- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData> m_HouseholdNeedCountData`  
- `private Game.Simulation.CountHouseholdDataSystem+HouseholdData m_LastHouseholdCountData`  
- `private Unity.Collections.NativeArray<System.Int32> m_ResourceNeed`  
- `private System.Boolean m_NeedForceCountData`  
- `private Unity.Collections.NativeArray<System.Int32> m_EmployableByEducation`  
- `private Game.Simulation.CountHouseholdDataSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Int32 MovingInHouseholdCount { get }`  
- `public System.Int32 MovingInCitizenCount { get }`  
- `public System.Int32 MovingAwayHouseholdCount { get }`  
- `public System.Int32 CommuterHouseholdCount { get }`  
- `public System.Int32 TouristCitizenCount { get }`  
- `public System.Int32 HomelessHouseholdCount { get }`  
- `public System.Int32 HomelessCitizenCount { get }`  
- `public System.Int32 MovedInHouseholdCount { get }`  
- `public System.Int32 MovedInCitizenCount { get }`  
- `public System.Int32 ChildrenCount { get }`  
- `public System.Int32 AdultCount { get }`  
- `public System.Int32 TeenCount { get }`  
- `public System.Int32 SeniorCount { get }`  
- `public System.Int32 StudentCount { get }`  
- `public System.Int32 UneducatedCount { get }`  
- `public System.Int32 PoorlyEducatedCount { get }`  
- `public System.Int32 EducatedCount { get }`  
- `public System.Int32 WellEducatedCount { get }`  
- `public System.Int32 HighlyEducatedCount { get }`  
- `public System.Int32 WorkableCitizenCount { get }`  
- `public System.Int32 CityWorkerCount { get }`  
- `public System.Int32 DeadCitizenCount { get }`  
- `public System.Int32 AverageCitizenHappiness { get }`  
- `public System.Int32 AverageCitizenHealth { get }`  
- `public System.Single UnemploymentRate { get }`  
- `public System.Single HomelessnessRate { get }`  

## Constructors

- `public CountHouseholdDataSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddHouseholdDataReader(Unity.Jobs.JobHandle reader) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetEmployables() : Unity.Collections.NativeArray<System.Int32>`  
- `public GetHouseholdCountData() : Game.Simulation.CountHouseholdDataSystem+HouseholdData`  
- `public GetResourceNeeds(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public IsCountDataNotReady() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData`  
- `Game.Simulation.CountHouseholdDataSystem+HouseholdData`  
- `Game.Simulation.CountHouseholdDataSystem+CountHouseholdJob`  
- `Game.Simulation.CountHouseholdDataSystem+ResultJob`  
- `Game.Simulation.CountHouseholdDataSystem+CitizenRequirementJob`  
- `Game.Simulation.CountHouseholdDataSystem+TypeHandle`  

