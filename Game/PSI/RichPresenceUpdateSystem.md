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
public RichPresenceUpdateSystem();
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
private System.Int32 GetAchievedMilestone();
```

- `private GetActionKey() : System.String`  

```csharp
private System.String GetActionKey();
```

- `private GetAverageHappiness() : System.Int32`  

```csharp
private System.Int32 GetAverageHappiness();
```

- `private GetAverageHealth() : System.Int32`  

```csharp
private System.Int32 GetAverageHealth();
```

- `private static GetHappinessIndex(System.Single happiness) : System.Int32`  

```csharp
private static System.Int32 GetHappinessIndex(System.Single happiness);
```

- `private static GetHealthIndex(System.Single health) : System.Int32`  

```csharp
private static System.Int32 GetHealthIndex(System.Single health);
```

- `private GetLightingState() : Game.Rendering.LightingSystem+State`  

```csharp
private Game.Rendering.LightingSystem+State GetLightingState();
```

- `private GetMilestoneKey(System.Int32 i) : System.String`  

```csharp
private System.String GetMilestoneKey(System.Int32 i);
```

- `private GetMilestoneNumber(System.Int32 i) : System.String`  

```csharp
private System.String GetMilestoneNumber(System.Int32 i);
```

- `private GetPopulationCount() : System.Int32`  

```csharp
private System.Int32 GetPopulationCount();
```

- `private GetWeatherIconKey() : System.String`  

```csharp
private System.String GetWeatherIconKey();
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

- `private RegisterKeys() : System.Void`  

```csharp
private System.Void RegisterKeys();
```

- `private UpdateEditorRichPresence() : System.Void`  

```csharp
private System.Void UpdateEditorRichPresence();
```

- `private UpdateGameRichPresence() : System.Void`  

```csharp
private System.Void UpdateGameRichPresence();
```


