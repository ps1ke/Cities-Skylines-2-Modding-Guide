# Game.Simulation.TradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ITradeSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Unity.Entities.EntityQuery m_StorageGroup`  
- `private Unity.Entities.EntityQuery m_TradeParameterQuery`  
- `private Unity.Entities.EntityQuery m_CityQuery`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Jobs.JobHandle m_DebugTradeBalanceDeps`  
- `private Unity.Collections.NativeArray<System.Int32> m_TradeBalances`  
- `private Unity.Collections.NativeArray<System.Single> m_CachedCosts`  
- `private Game.Simulation.TradeSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Single kRefreshRate`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public TradeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static CalculateTradeCost(Game.Economy.Resource resource, System.Int32 tradeBalance, Game.Prefabs.OutsideConnectionTransferType type, System.Single weight, Game.Prefabs.OutsideTradeParameterData& tradeParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : Game.Companies.TradeCost`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private static GetCacheIndex(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import) : System.Int32`  
- `public GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context context) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults() : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.TradeSystem+TradeJob`  
- `Game.Simulation.TradeSystem+TypeHandle`  

