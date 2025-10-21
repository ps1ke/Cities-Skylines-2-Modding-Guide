# Game.Simulation.GameModeGovernmentSubsidiesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GameModeGovernmentSubsidiesSystem : Game.GameSystemBase
{
    private System.Int32 m_LastSubsidyCoverPerDay;
    private System.Int32 m_MonthlySubsidy;
    private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    public static readonly System.Int32 kUpdatesPerDay;

    public System.Int32 LastSubsidyCoverPerDay { get; }
    public System.Int32 monthlySubsidy { get; }

    public GameModeGovernmentSubsidiesSystem();

    public System.Boolean GetGovernmentSubsidiesEnabled();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Int32 m_LastSubsidyCoverPerDay`  

```csharp
private System.Int32 m_LastSubsidyCoverPerDay;
```

- `private System.Int32 m_MonthlySubsidy`  

```csharp
private System.Int32 m_MonthlySubsidy;
```

- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  

```csharp
private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public System.Int32 LastSubsidyCoverPerDay { get }`  

```csharp
public System.Int32 LastSubsidyCoverPerDay { get; }
```

- `public System.Int32 monthlySubsidy { get }`  

```csharp
public System.Int32 monthlySubsidy { get; }
```


## Constructors

- `public GameModeGovernmentSubsidiesSystem()`  

```csharp
public GameModeGovernmentSubsidiesSystem();
```


## Methods

- `public GetGovernmentSubsidiesEnabled() : System.Boolean`  

```csharp
public System.Boolean GetGovernmentSubsidiesEnabled();
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


