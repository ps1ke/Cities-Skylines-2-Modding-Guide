# Game.PSI.RichPresenceUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.DateTime m_StartTime`  
- `private System.DateTime m_LastRichUpdate`  
- `private System.DateTime m_LastCycleUpdate`  
- `private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.UI.InGame.TimeUISystem m_TimeUISystem`  
- `private Game.UI.InGame.ClimateUISystem m_ClimateUISystem`  
- `private Unity.Entities.EntityQuery m_MilestoneLevelQuery`  
- `private System.Int32 m_StateIndex`  
- `private Colossal.PSI.Discord.DiscordRichPresence m_DiscordRichPresence`  
- `private System.String[] m_DiscordState`  
- `private static readonly System.String[] kHappinessEmoji`  
- `private static readonly System.String[] kHealthEmoji`  
- `private static readonly System.String[] kAltHealthEmoji`  
- `private static readonly System.String[] kAltHealth2Emoji`  
- `private static readonly System.String[] kRomanNumbers`  
- `private static const System.Int32 kUpdateRate`  
- `private static const System.Int32 kStateCycleInterval`  

## Properties

- `private Colossal.PSI.Discord.DiscordRichPresence discordRichPresence { private get }`  

## Constructors

- `public RichPresenceUpdateSystem()`  

## Methods

- `private <RegisterKeys>b__36_0() : System.String`  
- `private <RegisterKeys>b__36_1() : System.String`  
- `private <RegisterKeys>b__36_2() : System.String`  
- `private <RegisterKeys>b__36_3() : System.String`  
- `private <RegisterKeys>b__36_4() : System.String`  
- `private <RegisterKeys>b__36_5() : System.String`  
- `private <RegisterKeys>b__36_6() : System.String`  
- `private <RegisterKeys>b__36_7() : System.String`  
- `private <RegisterKeys>b__36_8() : System.String`  
- `private GetAchievedMilestone() : System.Int32`  
- `private GetActionKey() : System.String`  
- `private GetAverageHappiness() : System.Int32`  
- `private GetAverageHealth() : System.Int32`  
- `private static GetHappinessIndex(System.Single happiness) : System.Int32`  
- `private static GetHealthIndex(System.Single health) : System.Int32`  
- `private GetLightingState() : Game.Rendering.LightingSystem+State`  
- `private GetMilestoneKey(System.Int32 i) : System.String`  
- `private GetMilestoneNumber(System.Int32 i) : System.String`  
- `private GetPopulationCount() : System.Int32`  
- `private GetWeatherIconKey() : System.String`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RegisterKeys() : System.Void`  
- `private UpdateEditorRichPresence() : System.Void`  
- `private UpdateGameRichPresence() : System.Void`  

