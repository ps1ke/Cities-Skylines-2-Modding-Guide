# Game.Simulation.ProcessingCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  
- `private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_CompanyGroup`  
- `private Unity.Collections.NativeArray<System.Int64> m_ProducedResources`  
- `private Unity.Jobs.JobHandle m_ProducedResourcesDeps`  
- `private Game.Simulation.ProcessingCompanySystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1038562630_0`  
- `public static const System.Int32 kMaxCommercialOutputResource`  
- `public static const System.Single kMaximumTransportUnitCost`  

## Constructors

- `public ProcessingCompanySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddProducedResourcesReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetProducedResourcesArray(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeArray<System.Int64>`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.ProcessingCompanySystem+UpdateProcessingJob`  
- `Game.Simulation.ProcessingCompanySystem+TypeHandle`  

