# Game.Serialization.DataMigration.TradeCostFixSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TradeCostFixSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Simulation.TradeSystem m_TradeSystem;
    private Unity.Entities.EntityQuery m_TradeCostQuery;
    private Game.Serialization.DataMigration.TradeCostFixSystem+TypeHandle __TypeHandle;

    public TradeCostFixSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Simulation.TradeSystem m_TradeSystem`  

```csharp
private Game.Simulation.TradeSystem m_TradeSystem;
```

- `private Unity.Entities.EntityQuery m_TradeCostQuery`  

```csharp
private Unity.Entities.EntityQuery m_TradeCostQuery;
```

- `private Game.Serialization.DataMigration.TradeCostFixSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.TradeCostFixSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TradeCostFixSystem()`  

```csharp
public TradeCostFixSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Serialization.DataMigration.TradeCostFixSystem+TradeCostFixJob`  
- `Game.Serialization.DataMigration.TradeCostFixSystem+TypeHandle`  

