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
[Preserve]
	public EffectFlagSystem()
	{
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetData() : Game.Effects.EffectFlagSystem+EffectFlagData`  

```csharp
public EffectFlagData GetData()
	{
		return new EffectFlagData
		{
			m_IsColdSeason = m_IsColdSeason,
			m_IsNightTime = m_IsNightTime,
			m_LastSeasonChange = m_LastSeasonChange,
			m_LastTimeChange = m_LastTimeChange
		};
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 2048;
	}
```

- `public static IsEnabled(Game.Prefabs.EffectConditionFlags flag, Unity.Mathematics.Random random, Game.Effects.EffectFlagSystem+EffectFlagData data, System.UInt32 frame) : System.Boolean`  

```csharp
public static bool IsEnabled(EffectConditionFlags flag, Random random, EffectFlagData data, uint frame)
	{
		if ((flag & EffectConditionFlags.Night) != EffectConditionFlags.None)
		{
			if (data.m_IsNightTime)
			{
				return data.m_LastTimeChange + random.NextUInt(kNightRandomTicks) < frame;
			}
			return data.m_LastTimeChange + random.NextUInt(kDayRandomTicks) >= frame;
		}
		if ((flag & EffectConditionFlags.Cold) != EffectConditionFlags.None)
		{
			if (data.m_IsColdSeason)
			{
				return data.m_LastSeasonChange + random.NextUInt(kAutumnRandomTicks) < frame;
			}
			return data.m_LastSeasonChange + random.NextUInt(kSpringRandomTicks) >= frame;
		}
		return true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint frameIndex = m_SimulationSystem.frameIndex;
		if (m_CurrentSeason != m_ClimateSystem.currentSeason)
		{
			float num = m_ClimateSystem.temperature;
			if (m_IsColdSeason && num >= kSpringTemperature)
			{
				m_IsColdSeason = false;
				m_LastSeasonChange = frameIndex;
			}
			else if (!m_IsColdSeason && num < kAutumnTemperature)
			{
				m_IsColdSeason = true;
				m_LastSeasonChange = frameIndex;
			}
		}
		m_IsNightTime = m_TimeSystem.normalizedTime >= kNightBegin || m_TimeSystem.normalizedTime < kDayBegin;
		m_CurrentSeason = m_ClimateSystem.currentSeason;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_LastSeasonChange = 0u;
		m_IsColdSeason = false;
		m_IsNightTime = false;
		m_LastTimeChange = 0u;
	}
```


## Nested types

- `Game.Effects.EffectFlagSystem+EffectFlagData`  

