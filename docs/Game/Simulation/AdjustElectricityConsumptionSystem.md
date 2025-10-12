# Game.Simulation.AdjustElectricityConsumptionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  
- `private Unity.Entities.EntityQuery m_ConsumerQuery`  
- `private Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_653552652_0`  
- `private Unity.Entities.EntityQuery __query_653552652_1`  
- `private Unity.Entities.EntityQuery __query_653552652_2`  
- `private static const System.Int32 kFullUpdatesPerDay`  

## Constructors

- `public AdjustElectricityConsumptionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetFeeConsumptionMultiplier(System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters) : System.Single`  
- `public static GetFeeEfficiencyFactor(System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters) : System.Single`  
- `public GetTemperatureMultiplier(System.Single temperature) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AdjustElectricityConsumptionSystem+AdjustElectricityConsumptionJob`  
- `Game.Simulation.AdjustElectricityConsumptionSystem+UpdateEdgesJob`  
- `Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle`  

