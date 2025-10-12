# Game.Simulation.ServiceFeeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IServiceFeeSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_FeeCollectorGroup`  
- `private Unity.Entities.EntityQuery m_CollectedFeeGroup`  
- `private Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> m_FeeQueue`  
- `private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> m_CityServiceFees`  
- `private Unity.Jobs.JobHandle m_Writers`  
- `private Game.Simulation.ServiceFeeSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 kUpdatesPerDay`  

## Constructors

- `public ServiceFeeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddQueueWriter(Unity.Jobs.JobHandle deps) : System.Void`  
- `private CacheFees(System.Boolean reset = False) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public static GetConsumptionMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters) : System.Single`  
- `public static GetEducationResource(System.Int32 level) : Game.City.PlayerResource`  
- `public static GetEfficiencyMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters) : System.Single`  
- `public static GetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees) : System.Single`  
- `public GetFeeQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent>`  
- `public static GetHappinessEffect(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& happinessParameters) : System.Int32`  
- `public GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee) : System.Int32`  
- `public static GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees) : System.Int32`  
- `public GetServiceFees() : Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData>`  
- `public GetServiceFees(Game.City.PlayerResource resource) : Unity.Mathematics.int3`  
- `public static GetServiceFees(Game.City.PlayerResource resource, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees) : Unity.Mathematics.int3`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public static SetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single value) : System.Void`  
- `public static TryGetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single& fee) : System.Boolean`  

## Nested types

- `Game.Simulation.ServiceFeeSystem+FeeEvent`  
- `Game.Simulation.ServiceFeeSystem+PayFeeJob`  
- `Game.Simulation.ServiceFeeSystem+FeeToCityJob`  
- `Game.Simulation.ServiceFeeSystem+TriggerJob`  
- `Game.Simulation.ServiceFeeSystem+TypeHandle`  

