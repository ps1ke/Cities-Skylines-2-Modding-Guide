# Game.PSI.RichPresenceUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RichPresenceUpdateSystem : Game.GameSystemBase
{
    private System.DateTime m_StartTime;
    private System.DateTime m_LastRichUpdate;
    private System.DateTime m_LastCycleUpdate;
    private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.UI.InGame.TimeUISystem m_TimeUISystem;
    private Game.UI.InGame.ClimateUISystem m_ClimateUISystem;
    private Unity.Entities.EntityQuery m_MilestoneLevelQuery;
    private System.Int32 m_StateIndex;
    private Colossal.PSI.Discord.DiscordRichPresence m_DiscordRichPresence;
    private System.String[] m_DiscordState;
    private static readonly System.String[] kHappinessEmoji;
    private static readonly System.String[] kHealthEmoji;
    private static readonly System.String[] kAltHealthEmoji;
    private static readonly System.String[] kAltHealth2Emoji;
    private static readonly System.String[] kRomanNumbers;
    private static const System.Int32 kUpdateRate;
    private static const System.Int32 kStateCycleInterval;

    private Colossal.PSI.Discord.DiscordRichPresence discordRichPresence { private get; }

    public RichPresenceUpdateSystem();

    private System.String <RegisterKeys>b__36_0();
    private System.String <RegisterKeys>b__36_1();
    private System.String <RegisterKeys>b__36_2();
    private System.String <RegisterKeys>b__36_3();
    private System.String <RegisterKeys>b__36_4();
    private System.String <RegisterKeys>b__36_5();
    private System.String <RegisterKeys>b__36_6();
    private System.String <RegisterKeys>b__36_7();
    private System.String <RegisterKeys>b__36_8();
    private System.Int32 GetAchievedMilestone();
    private System.String GetActionKey();
    private System.Int32 GetAverageHappiness();
    private System.Int32 GetAverageHealth();
    private static System.Int32 GetHappinessIndex(System.Single happiness);
    private static System.Int32 GetHealthIndex(System.Single health);
    private Game.Rendering.LightingSystem+State GetLightingState();
    private System.String GetMilestoneKey(System.Int32 i);
    private System.String GetMilestoneNumber(System.Int32 i);
    private System.Int32 GetPopulationCount();
    private System.String GetWeatherIconKey();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RegisterKeys();
    private System.Void UpdateEditorRichPresence();
    private System.Void UpdateGameRichPresence();
}
```


## Fields

- `private System.DateTime m_StartTime`  

```csharp
private System.DateTime m_StartTime;
```

- `private System.DateTime m_LastRichUpdate`  

```csharp
private System.DateTime m_LastRichUpdate;
```

- `private System.DateTime m_LastCycleUpdate`  

```csharp
private System.DateTime m_LastCycleUpdate;
```

- `private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem`  

```csharp
private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.UI.InGame.TimeUISystem m_TimeUISystem`  

```csharp
private Game.UI.InGame.TimeUISystem m_TimeUISystem;
```

- `private Game.UI.InGame.ClimateUISystem m_ClimateUISystem`  

```csharp
private Game.UI.InGame.ClimateUISystem m_ClimateUISystem;
```

- `private Unity.Entities.EntityQuery m_MilestoneLevelQuery`  

```csharp
private Unity.Entities.EntityQuery m_MilestoneLevelQuery;
```

- `private System.Int32 m_StateIndex`  

```csharp
private System.Int32 m_StateIndex;
```

- `private Colossal.PSI.Discord.DiscordRichPresence m_DiscordRichPresence`  

```csharp
private Colossal.PSI.Discord.DiscordRichPresence m_DiscordRichPresence;
```

- `private System.String[] m_DiscordState`  

```csharp
private System.String[] m_DiscordState;
```

- `private static readonly System.String[] kHappinessEmoji`  

```csharp
private static readonly System.String[] kHappinessEmoji;
```

- `private static readonly System.String[] kHealthEmoji`  

```csharp
private static readonly System.String[] kHealthEmoji;
```

- `private static readonly System.String[] kAltHealthEmoji`  

```csharp
private static readonly System.String[] kAltHealthEmoji;
```

- `private static readonly System.String[] kAltHealth2Emoji`  

```csharp
private static readonly System.String[] kAltHealth2Emoji;
```

- `private static readonly System.String[] kRomanNumbers`  

```csharp
private static readonly System.String[] kRomanNumbers;
```

- `private static const System.Int32 kUpdateRate`  

```csharp
private static const System.Int32 kUpdateRate;
```

- `private static const System.Int32 kStateCycleInterval`  

```csharp
private static const System.Int32 kStateCycleInterval;
```


## Properties

- `private Colossal.PSI.Discord.DiscordRichPresence discordRichPresence { private get }`  

```csharp
private Colossal.PSI.Discord.DiscordRichPresence discordRichPresence { private get; }
```


## Constructors

- `public RichPresenceUpdateSystem()`  

```csharp
[Preserve]
	public RichPresenceUpdateSystem()
	{
	}
```


## Methods

- `private <RegisterKeys>b__36_0() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_0();
```

- `private <RegisterKeys>b__36_1() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_1();
```

- `private <RegisterKeys>b__36_2() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_2();
```

- `private <RegisterKeys>b__36_3() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_3();
```

- `private <RegisterKeys>b__36_4() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_4();
```

- `private <RegisterKeys>b__36_5() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_5();
```

- `private <RegisterKeys>b__36_6() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_6();
```

- `private <RegisterKeys>b__36_7() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_7();
```

- `private <RegisterKeys>b__36_8() : System.String`  

```csharp
private System.String <RegisterKeys>b__36_8();
```

- `private GetAchievedMilestone() : System.Int32`  

```csharp
private int GetAchievedMilestone()
	{
		if (m_MilestoneLevelQuery.IsEmptyIgnoreFilter)
		{
			return 0;
		}
		return m_MilestoneLevelQuery.GetSingleton<MilestoneLevel>().m_AchievedMilestone;
	}
```

- `private GetActionKey() : System.String`  

```csharp
private string GetActionKey()
	{
		if (m_PhotoModeRenderSystem.Enabled)
		{
			return "#StatusInGame_CapturingMemories";
		}
		if (m_ToolSystem.activeInfoview != null)
		{
			return "#StatusInGame_Inspecting";
		}
		if (m_ToolSystem.activeTool is BulldozeToolSystem)
		{
			return "#StatusInGame_Bulldozing";
		}
		return "#StatusInGame_Building";
	}
```

- `private GetAverageHappiness() : System.Int32`  

```csharp
private int GetAverageHappiness()
	{
		World defaultGameObjectInjectionWorld = World.DefaultGameObjectInjectionWorld;
		int result = 0;
		if (defaultGameObjectInjectionWorld.EntityManager.HasComponent<Population>(m_CitySystem.City))
		{
			result = defaultGameObjectInjectionWorld.EntityManager.GetComponentData<Population>(m_CitySystem.City).m_AverageHappiness;
		}
		return result;
	}
```

- `private GetAverageHealth() : System.Int32`  

```csharp
private int GetAverageHealth()
	{
		World defaultGameObjectInjectionWorld = World.DefaultGameObjectInjectionWorld;
		int result = 0;
		if (defaultGameObjectInjectionWorld.EntityManager.HasComponent<Population>(m_CitySystem.City))
		{
			result = defaultGameObjectInjectionWorld.EntityManager.GetComponentData<Population>(m_CitySystem.City).m_AverageHealth;
		}
		return result;
	}
```

- `private static GetHappinessIndex(System.Single happiness) : System.Int32`  

```csharp
private static int GetHappinessIndex(float happiness)
	{
		if (happiness > 70f)
		{
			return 4;
		}
		if (happiness > 55f)
		{
			return 3;
		}
		if (happiness > 40f)
		{
			return 2;
		}
		if (happiness > 25f)
		{
			return 1;
		}
		return 0;
	}
```

- `private static GetHealthIndex(System.Single health) : System.Int32`  

```csharp
private static int GetHealthIndex(float health)
	{
		if (health > 75f)
		{
			return 2;
		}
		if (health > 35f)
		{
			return 1;
		}
		return 0;
	}
```

- `private GetLightingState() : Game.Rendering.LightingSystem+State`  

```csharp
private LightingSystem.State GetLightingState()
	{
		LightingSystem.State lightingState = m_TimeUISystem.GetLightingState();
		switch (lightingState)
		{
		case LightingSystem.State.Sunset:
		case LightingSystem.State.Dusk:
			return LightingSystem.State.Night;
		case LightingSystem.State.Dawn:
		case LightingSystem.State.Sunrise:
			return LightingSystem.State.Day;
		default:
			return lightingState;
		}
	}
```

- `private GetMilestoneKey(System.Int32 i) : System.String`  

```csharp
private string GetMilestoneKey(int i)
	{
		return $"milestone{i}";
	}
```

- `private GetMilestoneNumber(System.Int32 i) : System.String`  

```csharp
private string GetMilestoneNumber(int i)
	{
		if (i == 0)
		{
			return null;
		}
		return kRomanNumbers[i - 1];
	}
```

- `private GetPopulationCount() : System.Int32`  

```csharp
private int GetPopulationCount()
	{
		World defaultGameObjectInjectionWorld = World.DefaultGameObjectInjectionWorld;
		int result = 0;
		if (defaultGameObjectInjectionWorld.EntityManager.HasComponent<Population>(m_CitySystem.City))
		{
			result = defaultGameObjectInjectionWorld.EntityManager.GetComponentData<Population>(m_CitySystem.City).m_Population;
		}
		return result;
	}
```

- `private GetWeatherIconKey() : System.String`  

```csharp
private string GetWeatherIconKey()
	{
		string text = m_ClimateSystem.classification.ToString().ToLowerInvariant();
		if ((float)m_ClimateSystem.precipitation > 0.3f)
		{
			if (m_ClimateSystem.isRaining)
			{
				text = "rain";
			}
			else if (m_ClimateSystem.isSnowing)
			{
				text = "snow";
			}
		}
		if (m_ClimateSystem.classification == ClimateSystem.WeatherClassification.Stormy && (float)m_ClimateSystem.precipitation > 0.9f)
		{
			text = ((!m_ClimateSystem.isRaining) ? "hail" : "stormy");
		}
		string text2 = GetLightingState().ToString().ToLowerInvariant();
		return text + text2;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_ClimateUISystem = base.World.GetOrCreateSystemManaged<ClimateUISystem>();
		m_TimeUISystem = base.World.GetOrCreateSystemManaged<TimeUISystem>();
		m_PhotoModeRenderSystem = base.World.GetOrCreateSystemManaged<PhotoModeRenderSystem>();
		m_MilestoneLevelQuery = GetEntityQuery(ComponentType.ReadOnly<MilestoneLevel>());
		RegisterKeys();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_StartTime = DateTime.Now;
		if (GameManager.instance.gameMode.IsGame())
		{
			m_DiscordState = new string[5] { "#StatusInGame_Population", "#StatusInGame_Money", "#StatusInGame_Happiness", "#StatusInGame_Health", "#StatusInGame_Milestone" };
		}
		else
		{
			GameManager.instance.gameMode.IsEditor();
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		try
		{
			DateTime now = DateTime.Now;
			if ((now - m_LastRichUpdate).TotalSeconds < 5.0)
			{
				return;
			}
			GameMode gameMode = GameManager.instance.gameMode;
			if (gameMode.IsGameOrEditor())
			{
				if ((now - m_LastCycleUpdate).TotalSeconds > 10.0)
				{
					m_StateIndex++;
					m_LastCycleUpdate = now;
				}
				if (gameMode.IsGame())
				{
					UpdateGameRichPresence();
				}
				else if (gameMode.IsEditor())
				{
					UpdateEditorRichPresence();
				}
			}
			m_LastRichUpdate = now;
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Warn(exception);
		}
	}
```

- `private RegisterKeys() : System.Void`  

```csharp
private void RegisterKeys()
	{
		PlatformManager instance = PlatformManager.instance;
		instance.RegisterRichPresenceKey("#StatusInGame_Building", () => "Building " + m_CityConfigurationSystem.cityName);
		instance.RegisterRichPresenceKey("#StatusInGame_Bulldozing", () => "Bulldozing " + m_CityConfigurationSystem.cityName);
		instance.RegisterRichPresenceKey("#StatusInGame_Inspecting", () => "Inspecting " + m_CityConfigurationSystem.cityName);
		instance.RegisterRichPresenceKey("#StatusInGame_CapturingMemories", () => "Capturing memories in " + m_CityConfigurationSystem.cityName);
		instance.RegisterRichPresenceKey("#StatusInGame_Population", () => $"Population: {GetPopulationCount()}");
		instance.RegisterRichPresenceKey("#StatusInGame_Money", () => "Money: " + m_CitySystem.moneyAmount.ToString(CultureInfo.InvariantCulture) + "¢");
		instance.RegisterRichPresenceKey("#StatusInGame_Happiness", () => "Happiness: " + kHappinessEmoji[GetHappinessIndex(GetAverageHappiness())]);
		instance.RegisterRichPresenceKey("#StatusInGame_Health", () => "Health: " + kHealthEmoji[GetHealthIndex(GetAverageHealth())]);
		instance.RegisterRichPresenceKey("#StatusInGame_Milestone", () => "Milestone " + GetMilestoneNumber(GetAchievedMilestone()));
	}
```

- `private UpdateEditorRichPresence() : System.Void`  

```csharp
private void UpdateEditorRichPresence()
	{
		discordRichPresence.SetRichPresence("In Editor", "Authoring UGC...", m_StartTime, "editor", "In-Game Editor");
	}
```

- `private UpdateGameRichPresence() : System.Void`  

```csharp
private void UpdateGameRichPresence()
	{
		int achievedMilestone = GetAchievedMilestone();
		string milestoneNumber = GetMilestoneNumber(achievedMilestone);
		if (m_DiscordState != null)
		{
			discordRichPresence.SetRichPresence(GetActionKey(), m_DiscordState[m_StateIndex % ((achievedMilestone == 0) ? (m_DiscordState.Length - 1) : m_DiscordState.Length)], m_StartTime, GetMilestoneKey(achievedMilestone), (milestoneNumber != null) ? ("Milestone " + milestoneNumber) : null, GetWeatherIconKey(), $"{math.round(m_ClimateSystem.temperature)}°C");
		}
	}
```


