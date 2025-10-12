# Game.Simulation.WaterTradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  
- `private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem`  
- `private Unity.Entities.EntityQuery m_TradeNodeGroup`  
- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  
- `private Colossal.NativePerThreadSumInt m_FreshExport`  
- `private Colossal.NativePerThreadSumInt m_PollutedExport`  
- `private Colossal.NativePerThreadSumInt m_FreshImport`  
- `private Colossal.NativePerThreadSumInt m_SewageExport`  
- `private System.Int32 m_LastFreshExport`  
- `private System.Int32 m_LastFreshImport`  
- `private System.Int32 m_LastSewageExport`  
- `private Game.Simulation.WaterTradeSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1457460959_0`  

## Properties

- `public System.Int32 freshExport { get }`  
- `public System.Int32 freshImport { get }`  
- `public System.Int32 sewageExport { get }`  

## Constructors

- `public WaterTradeSystem()`  

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

- `Game.Simulation.WaterTradeSystem+SumJob`  
- `Game.Simulation.WaterTradeSystem+WaterTradeJob`  
- `Game.Simulation.WaterTradeSystem+TypeHandle`  

