# Game.Simulation.WaterTradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterTradeSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem;
    private Unity.Entities.EntityQuery m_TradeNodeGroup;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Colossal.NativePerThreadSumInt m_FreshExport;
    private Colossal.NativePerThreadSumInt m_PollutedExport;
    private Colossal.NativePerThreadSumInt m_FreshImport;
    private Colossal.NativePerThreadSumInt m_SewageExport;
    private System.Int32 m_LastFreshExport;
    private System.Int32 m_LastFreshImport;
    private System.Int32 m_LastSewageExport;
    private Game.Simulation.WaterTradeSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1457460959_0;

    public System.Int32 freshExport { get; }
    public System.Int32 freshImport { get; }
    public System.Int32 sewageExport { get; }

    public WaterTradeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem`  

```csharp
private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_TradeNodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_TradeNodeGroup;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Colossal.NativePerThreadSumInt m_FreshExport`  

```csharp
private Colossal.NativePerThreadSumInt m_FreshExport;
```

- `private Colossal.NativePerThreadSumInt m_PollutedExport`  

```csharp
private Colossal.NativePerThreadSumInt m_PollutedExport;
```

- `private Colossal.NativePerThreadSumInt m_FreshImport`  

```csharp
private Colossal.NativePerThreadSumInt m_FreshImport;
```

- `private Colossal.NativePerThreadSumInt m_SewageExport`  

```csharp
private Colossal.NativePerThreadSumInt m_SewageExport;
```

- `private System.Int32 m_LastFreshExport`  

```csharp
private System.Int32 m_LastFreshExport;
```

- `private System.Int32 m_LastFreshImport`  

```csharp
private System.Int32 m_LastFreshImport;
```

- `private System.Int32 m_LastSewageExport`  

```csharp
private System.Int32 m_LastSewageExport;
```

- `private Game.Simulation.WaterTradeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterTradeSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1457460959_0`  

```csharp
private Unity.Entities.EntityQuery __query_1457460959_0;
```


## Properties

- `public System.Int32 freshExport { get }`  

```csharp
public System.Int32 freshExport { get; }
```

- `public System.Int32 freshImport { get }`  

```csharp
public System.Int32 freshImport { get; }
```

- `public System.Int32 sewageExport { get }`  

```csharp
public System.Int32 sewageExport { get; }
```


## Constructors

- `public WaterTradeSystem()`  

```csharp
public WaterTradeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.WaterTradeSystem+SumJob`  
- `Game.Simulation.WaterTradeSystem+WaterTradeJob`  
- `Game.Simulation.WaterTradeSystem+TypeHandle`  

