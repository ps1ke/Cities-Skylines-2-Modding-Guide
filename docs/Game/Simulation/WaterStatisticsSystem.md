# Game.Simulation.WaterStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IWaterStatisticsSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_PumpGroup`  
- `private Unity.Entities.EntityQuery m_OutletGroup`  
- `private Unity.Entities.EntityQuery m_ConsumerGroup`  
- `private Colossal.NativePerThreadSumInt m_FreshCapacity`  
- `private Colossal.NativePerThreadSumInt m_SewageCapacity`  
- `private Colossal.NativePerThreadSumInt m_Consumption`  
- `private Colossal.NativePerThreadSumInt m_FulfilledFreshConsumption`  
- `private Colossal.NativePerThreadSumInt m_FulfilledSewageConsumption`  
- `private System.Int32 m_LastFreshCapacity`  
- `private System.Int32 m_LastFreshConsumption`  
- `private System.Int32 m_LastFulfilledFreshConsumption`  
- `private System.Int32 m_LastSewageCapacity`  
- `private System.Int32 m_LastSewageConsumption`  
- `private System.Int32 m_LastFulfilledSewageConsumption`  
- `private Game.Simulation.WaterStatisticsSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Int32 freshCapacity { get }`  
- `public System.Int32 freshConsumption { get }`  
- `public System.Int32 fulfilledFreshConsumption { get }`  
- `public System.Int32 sewageCapacity { get }`  
- `public System.Int32 sewageConsumption { get }`  
- `public System.Int32 fulfilledSewageConsumption { get }`  

## Constructors

- `public WaterStatisticsSystem()`  

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

- `Game.Simulation.WaterStatisticsSystem+CountPumpCapacityJob`  
- `Game.Simulation.WaterStatisticsSystem+CountOutletCapacityJob`  
- `Game.Simulation.WaterStatisticsSystem+CountWaterConsumptionJob`  
- `Game.Simulation.WaterStatisticsSystem+TypeHandle`  

