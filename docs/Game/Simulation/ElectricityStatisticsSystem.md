# Game.Simulation.ElectricityStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IElectricityStatisticsSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ProducerGroup`  
- `private Unity.Entities.EntityQuery m_ConsumerGroup`  
- `private Unity.Entities.EntityQuery m_BatteryGroup`  
- `private Colossal.NativePerThreadSumInt m_Production`  
- `private Colossal.NativePerThreadSumInt m_Consumption`  
- `private Colossal.NativePerThreadSumInt m_FulfilledConsumption`  
- `private Colossal.NativePerThreadSumInt m_BatteryCharge`  
- `private Colossal.NativePerThreadSumInt m_BatteryCapacity`  
- `private System.Int32 m_LastProduction`  
- `private System.Int32 m_LastConsumption`  
- `private System.Int32 m_LastFulfilledConsumption`  
- `private System.Int32 m_LastBatteryCharge`  
- `private System.Int32 m_LastBatteryCapacity`  
- `private Game.Simulation.ElectricityStatisticsSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Int32 production { get }`  
- `public System.Int32 consumption { get }`  
- `public System.Int32 fulfilledConsumption { get }`  
- `public System.Int32 batteryCharge { get }`  
- `public System.Int32 batteryCapacity { get }`  

## Constructors

- `public ElectricityStatisticsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.ElectricityStatisticsSystem+CountElectricityProductionJob`  
- `Game.Simulation.ElectricityStatisticsSystem+CountElectricityConsumptionJob`  
- `Game.Simulation.ElectricityStatisticsSystem+CountBatteryCapacityJob`  
- `Game.Simulation.ElectricityStatisticsSystem+TypeHandle`  

