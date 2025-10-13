# Game.Simulation.TradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ITradeSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TradeSystem : Game.GameSystemBase, Game.Simulation.ITradeSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_StorageGroup;
    private Unity.Entities.EntityQuery m_TradeParameterQuery;
    private Unity.Entities.EntityQuery m_CityQuery;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Jobs.JobHandle m_DebugTradeBalanceDeps;
    private Unity.Collections.NativeArray<System.Int32> m_TradeBalances;
    private Unity.Collections.NativeArray<System.Single> m_CachedCosts;
    private Game.Simulation.TradeSystem+TypeHandle __TypeHandle;
    private static readonly System.Single kRefreshRate;
    public static readonly System.Int32 kUpdatesPerDay;

    public TradeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static Game.Companies.TradeCost CalculateTradeCost(Game.Economy.Resource resource, System.Int32 tradeBalance, Game.Prefabs.OutsideConnectionTransferType type, System.Single weight, Game.Prefabs.OutsideTradeParameterData& tradeParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
    public System.Void Deserialize<TReader>(TReader reader);
    private static System.Int32 GetCacheIndex(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import);
    public System.Single GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context context);
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults();
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_StorageGroup`  

```csharp
private Unity.Entities.EntityQuery m_StorageGroup;
```

- `private Unity.Entities.EntityQuery m_TradeParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_TradeParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CityQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityQuery;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Jobs.JobHandle m_DebugTradeBalanceDeps`  

```csharp
private Unity.Jobs.JobHandle m_DebugTradeBalanceDeps;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TradeBalances`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TradeBalances;
```

- `private Unity.Collections.NativeArray<System.Single> m_CachedCosts`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_CachedCosts;
```

- `private Game.Simulation.TradeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TradeSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single kRefreshRate`  

```csharp
private static readonly System.Single kRefreshRate;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public TradeSystem()`  

```csharp
public TradeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static CalculateTradeCost(Game.Economy.Resource resource, System.Int32 tradeBalance, Game.Prefabs.OutsideConnectionTransferType type, System.Single weight, Game.Prefabs.OutsideTradeParameterData& tradeParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : Game.Companies.TradeCost`  

```csharp
private static Game.Companies.TradeCost CalculateTradeCost(Game.Economy.Resource resource, System.Int32 tradeBalance, Game.Prefabs.OutsideConnectionTransferType type, System.Single weight, Game.Prefabs.OutsideTradeParameterData& tradeParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private static GetCacheIndex(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import) : System.Int32`  

```csharp
private static System.Int32 GetCacheIndex(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import);
```

- `public GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Single`  

```csharp
public System.Single GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context context);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults() : System.Void`  

```csharp
public System.Void SetDefaults();
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.TradeSystem+TradeJob`  
- `Game.Simulation.TradeSystem+TypeHandle`  

