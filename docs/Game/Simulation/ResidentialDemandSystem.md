# Game.Simulation.ResidentialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem`  
- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  
- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  
- `private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Unity.Entities.EntityQuery m_DemandParameterGroup`  
- `private Unity.Entities.EntityQuery m_UnlockedZonePrefabQuery`  
- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  
- `private Colossal.Collections.NativeValue<System.Int32> m_HouseholdDemand`  
- `private Colossal.Collections.NativeValue<Unity.Mathematics.int3> m_BuildingDemand`  
- `private Unity.Collections.NativeArray<System.Int32> m_LowDemandFactors`  
- `private Unity.Collections.NativeArray<System.Int32> m_MediumDemandFactors`  
- `private Unity.Collections.NativeArray<System.Int32> m_HighDemandFactors`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private System.Int32 m_LastHouseholdDemand`  
- `private Unity.Mathematics.int3 m_LastBuildingDemand`  
- `private Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector`  
- `private Game.Simulation.ResidentialDemandSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kMaxFactorEffect`  

## Properties

- `public System.Int32 householdDemand { get }`  
- `public Unity.Mathematics.int3 buildingDemand { get }`  

## Constructors

- `public ResidentialDemandSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetHighDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetLowDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetMediumDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.ResidentialDemandSystem+UpdateResidentialDemandJob`  
- `Game.Simulation.ResidentialDemandSystem+TypeHandle`  

