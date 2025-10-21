# Game.Simulation.ElectricityTradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityTradeSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Unity.Entities.EntityQuery m_TradeNodeGroup;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Colossal.NativePerThreadSumInt m_Export;
    private Colossal.NativePerThreadSumInt m_Import;
    private System.Int32 m_LastExport;
    private System.Int32 m_LastImport;
    private Game.Simulation.ElectricityTradeSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1233563293_0;

    public System.Int32 export { get; }
    public System.Int32 import { get; }

    public ElectricityTradeSystem();

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

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Unity.Entities.EntityQuery m_TradeNodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_TradeNodeGroup;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Colossal.NativePerThreadSumInt m_Export`  

```csharp
private Colossal.NativePerThreadSumInt m_Export;
```

- `private Colossal.NativePerThreadSumInt m_Import`  

```csharp
private Colossal.NativePerThreadSumInt m_Import;
```

- `private System.Int32 m_LastExport`  

```csharp
private System.Int32 m_LastExport;
```

- `private System.Int32 m_LastImport`  

```csharp
private System.Int32 m_LastImport;
```

- `private Game.Simulation.ElectricityTradeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityTradeSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1233563293_0`  

```csharp
private Unity.Entities.EntityQuery __query_1233563293_0;
```


## Properties

- `public System.Int32 export { get }`  

```csharp
public System.Int32 export { get; }
```

- `public System.Int32 import { get }`  

```csharp
public System.Int32 import { get; }
```


## Constructors

- `public ElectricityTradeSystem()`  

```csharp
public ElectricityTradeSystem();
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

- `Game.Simulation.ElectricityTradeSystem+SumJob`  
- `Game.Simulation.ElectricityTradeSystem+ElectricityTradeJob`  
- `Game.Simulation.ElectricityTradeSystem+TypeHandle`  

