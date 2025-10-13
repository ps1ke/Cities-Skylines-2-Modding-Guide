# Game.Effects.EffectFlagSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public class EffectFlagSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.Entity m_CurrentSeason;
    private System.UInt32 m_LastSeasonChange;
    private System.Boolean m_IsColdSeason;
    private System.Boolean m_IsNightTime;
    private System.UInt32 m_LastTimeChange;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    public static readonly System.UInt32 kNightRandomTicks;
    public static readonly System.UInt32 kDayRandomTicks;
    public static readonly System.Single kNightBegin;
    public static readonly System.Single kDayBegin;
    public static readonly System.UInt32 kSpringRandomTicks;
    public static readonly System.UInt32 kAutumnRandomTicks;
    public static readonly System.Single kSpringTemperature;
    public static readonly System.Single kAutumnTemperature;

    public EffectFlagSystem();

    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Effects.EffectFlagSystem+EffectFlagData GetData();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Boolean IsEnabled(Game.Prefabs.EffectConditionFlags flag, Unity.Mathematics.Random random, Game.Effects.EffectFlagSystem+EffectFlagData data, System.UInt32 frame);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.Entity m_CurrentSeason`  

```csharp
private Unity.Entities.Entity m_CurrentSeason;
```

- `private System.UInt32 m_LastSeasonChange`  

```csharp
private System.UInt32 m_LastSeasonChange;
```

- `private System.Boolean m_IsColdSeason`  

```csharp
private System.Boolean m_IsColdSeason;
```

- `private System.Boolean m_IsNightTime`  

```csharp
private System.Boolean m_IsNightTime;
```

- `private System.UInt32 m_LastTimeChange`  

```csharp
private System.UInt32 m_LastTimeChange;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `public static readonly System.UInt32 kNightRandomTicks`  

```csharp
public static readonly System.UInt32 kNightRandomTicks;
```

- `public static readonly System.UInt32 kDayRandomTicks`  

```csharp
public static readonly System.UInt32 kDayRandomTicks;
```

- `public static readonly System.Single kNightBegin`  

```csharp
public static readonly System.Single kNightBegin;
```

- `public static readonly System.Single kDayBegin`  

```csharp
public static readonly System.Single kDayBegin;
```

- `public static readonly System.UInt32 kSpringRandomTicks`  

```csharp
public static readonly System.UInt32 kSpringRandomTicks;
```

- `public static readonly System.UInt32 kAutumnRandomTicks`  

```csharp
public static readonly System.UInt32 kAutumnRandomTicks;
```

- `public static readonly System.Single kSpringTemperature`  

```csharp
public static readonly System.Single kSpringTemperature;
```

- `public static readonly System.Single kAutumnTemperature`  

```csharp
public static readonly System.Single kAutumnTemperature;
```


## Constructors

- `public EffectFlagSystem()`  

```csharp
public EffectFlagSystem();
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetData() : Game.Effects.EffectFlagSystem+EffectFlagData`  

```csharp
public Game.Effects.EffectFlagSystem+EffectFlagData GetData();
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static IsEnabled(Game.Prefabs.EffectConditionFlags flag, Unity.Mathematics.Random random, Game.Effects.EffectFlagSystem+EffectFlagData data, System.UInt32 frame) : System.Boolean`  

```csharp
public static System.Boolean IsEnabled(Game.Prefabs.EffectConditionFlags flag, Unity.Mathematics.Random random, Game.Effects.EffectFlagSystem+EffectFlagData data, System.UInt32 frame);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
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

- `Game.Effects.EffectFlagSystem+EffectFlagData`  

