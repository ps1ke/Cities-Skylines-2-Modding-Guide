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
[Preserve]
	public GameModeGovernmentSubsidiesSystem()
	{
	}
```


## Methods

- `public GetGovernmentSubsidiesEnabled() : System.Boolean`  

```csharp
public bool GetGovernmentSubsidiesEnabled()
	{
		return base.Enabled;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityServiceBudgetSystem = base.World.GetOrCreateSystemManaged<CityServiceBudgetSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_GameModeSettingQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<ModeSettingData>());
		RequireForUpdate(m_GameModeSettingQuery);
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_MonthlySubsidy = 0;
		if (m_GameModeSettingQuery.IsEmptyIgnoreFilter)
		{
			base.Enabled = false;
			return;
		}
		ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
		if (singleton.m_Enable && singleton.m_EnableGovernmentSubsidies)
		{
			base.Enabled = true;
		}
		else
		{
			base.Enabled = false;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_MonthlySubsidy = 0;
		if (m_GameModeSettingQuery.IsEmptyIgnoreFilter || m_CitySystem.City == Entity.Null)
		{
			return;
		}
		ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
		PlayerMoney componentData = base.EntityManager.GetComponentData<PlayerMoney>(m_CitySystem.City);
		if (componentData.money < singleton.m_MoneyCoverThreshold.x)
		{
			float num = singleton.m_MoneyCoverThreshold.x - singleton.m_MoneyCoverThreshold.y;
			float num2 = math.clamp(1f - (float)(componentData.money - singleton.m_MoneyCoverThreshold.y) / num, 0f, 1f) * ((float)singleton.m_MaxMoneyCoverPercentage / 100f);
			if (num2 > 0f)
			{
				m_MonthlySubsidy = math.abs((int)(num2 * (float)m_CityServiceBudgetSystem.GetTotalExpenses()));
				m_LastSubsidyCoverPerDay = m_MonthlySubsidy / kUpdatesPerDay;
			}
		}
	}
```


