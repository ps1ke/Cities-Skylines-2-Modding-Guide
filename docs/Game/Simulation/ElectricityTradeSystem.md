# Game.Simulation.ElectricityTradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  
- `private Unity.Entities.EntityQuery m_TradeNodeGroup`  
- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  
- `private Colossal.NativePerThreadSumInt m_Export`  
- `private Colossal.NativePerThreadSumInt m_Import`  
- `private System.Int32 m_LastExport`  
- `private System.Int32 m_LastImport`  
- `private Game.Simulation.ElectricityTradeSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1233563293_0`  

## Properties

- `public System.Int32 export { get }`  
- `public System.Int32 import { get }`  

## Constructors

- `public ElectricityTradeSystem()`  

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

- `Game.Simulation.ElectricityTradeSystem+SumJob`  
- `Game.Simulation.ElectricityTradeSystem+ElectricityTradeJob`  
- `Game.Simulation.ElectricityTradeSystem+TypeHandle`  

