# Game.PSI.Telemetry

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Telemetry`  

## Code

```csharp
public static class Telemetry
{
    private static Colossal.Logging.ILog log;
    private static Game.PSI.Telemetry+GameplayData <gameplayData>k__BackingField;
    private static Game.PSI.Telemetry+Session s_Session;
    private static const System.String kHardwareEvent;
    private static const System.String kLanguageEvent;
    private static const System.String kGraphicsSettings;
    private static const System.String kAchievementUnlocked;
    private static const System.String kTutorialEvent;
    private static const System.String kMilestoneUnlocked;
    private static const System.String kDevNodePurchased;
    private static const System.String kControlInput;
    private static const System.String kPanelClosed;
    private static const System.String kCityStats;
    private static const System.String kChirper;
    private static const System.String kBuildingPlaced;
    private static const System.String kPolicy;
    private static const System.String kInputIdleEnd;
    private static const System.String kSessionOpen;
    private static const System.String kSessionClose;
    private static const System.String kModsUsed;
    private static const System.String kDlc;

    public static Game.PSI.Telemetry+GameplayData gameplayData { get; set; }

    public static System.Void AchievementUnlocked(Colossal.PSI.Common.AchievementId id);
    public static System.Void Chirp(Unity.Entities.Entity chirpPrefab, System.UInt32 likes);
    public static System.Void CityStats();
    public static System.Void CloseSession();
    public static System.Void ControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme);
    public static System.Void DevNodePurchased(Game.Prefabs.DevTreeNodePrefab nodePrefab);
    private static System.Void DlcsInstalled(Game.PSI.Telemetry+GameplayData data);
    public static System.Void FireSessionStartEvents();
    public static System.Guid GetCurrentSession();
    public static System.Void GraphicsSettings();
    private static System.Void Hardware();
    public static System.Void InputIdleEnd();
    public static System.Void InputIdleStart();
    private static System.Void Language();
    public static System.Void MilestoneUnlocked(System.Int32 milestoneIndex);
    private static System.Void ModsUsed();
    public static System.Void OpenSession(System.Guid guid);
    public static System.Void PanelClosed(Game.UI.InGame.GamePanel panel);
    public static System.Void PanelOpened(Game.UI.InGame.GamePanel panel);
    public static System.Void PlaceBuilding(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase building, Unity.Mathematics.float3 position);
    public static System.Void Policy(Game.Policies.ModifiedSystem+PolicyEventInfo eventInfo);
    public static System.Void TutorialEvent(Unity.Entities.Entity tutorial);
}
```


## Fields

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static Game.PSI.Telemetry+GameplayData <gameplayData>k__BackingField`  

```csharp
private static Game.PSI.Telemetry+GameplayData <gameplayData>k__BackingField;
```

- `private static Game.PSI.Telemetry+Session s_Session`  

```csharp
private static Game.PSI.Telemetry+Session s_Session;
```

- `private static const System.String kHardwareEvent`  

```csharp
private static const System.String kHardwareEvent;
```

- `private static const System.String kLanguageEvent`  

```csharp
private static const System.String kLanguageEvent;
```

- `private static const System.String kGraphicsSettings`  

```csharp
private static const System.String kGraphicsSettings;
```

- `private static const System.String kAchievementUnlocked`  

```csharp
private static const System.String kAchievementUnlocked;
```

- `private static const System.String kTutorialEvent`  

```csharp
private static const System.String kTutorialEvent;
```

- `private static const System.String kMilestoneUnlocked`  

```csharp
private static const System.String kMilestoneUnlocked;
```

- `private static const System.String kDevNodePurchased`  

```csharp
private static const System.String kDevNodePurchased;
```

- `private static const System.String kControlInput`  

```csharp
private static const System.String kControlInput;
```

- `private static const System.String kPanelClosed`  

```csharp
private static const System.String kPanelClosed;
```

- `private static const System.String kCityStats`  

```csharp
private static const System.String kCityStats;
```

- `private static const System.String kChirper`  

```csharp
private static const System.String kChirper;
```

- `private static const System.String kBuildingPlaced`  

```csharp
private static const System.String kBuildingPlaced;
```

- `private static const System.String kPolicy`  

```csharp
private static const System.String kPolicy;
```

- `private static const System.String kInputIdleEnd`  

```csharp
private static const System.String kInputIdleEnd;
```

- `private static const System.String kSessionOpen`  

```csharp
private static const System.String kSessionOpen;
```

- `private static const System.String kSessionClose`  

```csharp
private static const System.String kSessionClose;
```

- `private static const System.String kModsUsed`  

```csharp
private static const System.String kModsUsed;
```

- `private static const System.String kDlc`  

```csharp
private static const System.String kDlc;
```


## Properties

- `public static Game.PSI.Telemetry+GameplayData gameplayData { get; set }`  

```csharp
public static Game.PSI.Telemetry+GameplayData gameplayData { get; set; }
```


## Methods

- `public static AchievementUnlocked(Colossal.PSI.Common.AchievementId id) : System.Void`  

```csharp
public static void AchievementUnlocked(AchievementId id)
	{
		try
		{
			if (s_Session.active && PlatformManager.instance.GetAchievement(id, out var achievement) && achievement.achieved)
			{
				AchievementPayload payload = new AchievementPayload
				{
					playthrough_id = s_Session.guid,
					achievement_name = achievement.internalName,
					achievement_number = PlatformManager.instance.CountAchievements(onlyAchieved: true)
				};
				PlatformManager.instance.SendTelemetry("achievement", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "achievement");
		}
	}
```

- `public static Chirp(Unity.Entities.Entity chirpPrefab, System.UInt32 likes) : System.Void`  

```csharp
public static void Chirp(Entity chirpPrefab, uint likes)
	{
		try
		{
			if (gameplayData != null && s_Session.active)
			{
				PrefabBase prefab = gameplayData.GetPrefab<PrefabBase>(chirpPrefab);
				ChirperPayload payload = new ChirperPayload
				{
					playthrough_id = s_Session.guid,
					message_type = prefab.name,
					likes = likes
				};
				PlatformManager.instance.SendTelemetry("chirper", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "chirper");
		}
	}
```

- `public static CityStats() : System.Void`  

```csharp
public static void CityStats()
	{
		try
		{
			if (gameplayData != null && s_Session.active)
			{
				Population population = gameplayData.population;
				CityStatsPayload payload = new CityStatsPayload
				{
					playthrough_id = s_Session.guid,
					map_id = gameplayData.mapName,
					n_buildings = gameplayData.buildingCount,
					population = population.m_Population,
					happiness = population.m_AverageHappiness,
					ingame_days = gameplayData.GetDay(),
					map_tiles = gameplayData.ownedMapTiles,
					resource_output = gameplayData.GetResourcesOutputCount(),
					cash_balance = gameplayData.moneyAmount,
					cash_income = gameplayData.moneyDelta,
					tagged_citizens = gameplayData.followedCitizens
				};
				PlatformManager.instance.SendTelemetry("city_stats", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "city_stats");
		}
	}
```

- `public static CloseSession() : System.Void`  

```csharp
public static void CloseSession()
	{
		try
		{
			if (gameplayData != null && s_Session.active)
			{
				CloseSessionPayload payload = new CloseSessionPayload
				{
					playthrough_id = s_Session.guid,
					map_id = gameplayData.mapName,
					ingame_days = gameplayData.GetDay(),
					time_passed = Math.Round(s_Session.duration.TotalHours, 2)
				};
				PlatformManager.instance.SendTelemetry("playsession_close", payload);
				s_Session.Close();
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "playsession_close");
		}
	}
```

- `public static ControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  

```csharp
public static void ControlSchemeChanged(InputManager.ControlScheme controlScheme)
	{
		try
		{
			if (s_Session.active)
			{
				ControlInputPayload payload = new ControlInputPayload
				{
					playthrough_id = s_Session.guid,
					control_scheme = controlScheme.ToString()
				};
				PlatformManager.instance.SendTelemetry("control_input", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "control_input");
		}
	}
```

- `public static DevNodePurchased(Game.Prefabs.DevTreeNodePrefab nodePrefab) : System.Void`  

```csharp
public static void DevNodePurchased(DevTreeNodePrefab nodePrefab)
	{
		try
		{
			if (s_Session.active)
			{
				DevNodePurchasedPayload payload = new DevNodePurchasedPayload
				{
					playthrough_id = s_Session.guid,
					dev_node_name = nodePrefab.name,
					node_type = nodePrefab.m_Service.name,
					tier_id = nodePrefab.m_HorizontalPosition
				};
				PlatformManager.instance.SendTelemetry("dev_node", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "dev_node");
		}
	}
```

- `private static DlcsInstalled(Game.PSI.Telemetry+GameplayData data) : System.Void`  

```csharp
private static void DlcsInstalled(GameplayData data)
	{
		try
		{
			DlcPayload payload = new DlcPayload
			{
				dlcs = (from dlc in PlatformManager.instance.EnumerateDLCs()
					where dlc.hasStoreBackend
					select new DlcPayload.Dlc
					{
						dlc_name = dlc.internalName,
						dlc_platform_id = dlc.backendId
					}).ToArray()
			};
			if (payload.dlcs.Any())
			{
				PlatformManager.instance.SendTelemetry("dlc", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "dlc");
		}
	}
```

- `public static FireSessionStartEvents() : System.Void`  

```csharp
public static void FireSessionStartEvents()
	{
		Hardware();
		Language();
		GraphicsSettings();
	}
```

- `public static GetCurrentSession() : System.Guid`  

```csharp
public static Guid GetCurrentSession()
	{
		return s_Session.guid;
	}
```

- `public static GraphicsSettings() : System.Void`  

```csharp
public static void GraphicsSettings()
	{
		try
		{
			GraphicsSettingsPayload payload = new GraphicsSettingsPayload
			{
				display_mode = SharedSettings.instance.graphics.displayMode.ToTelemetry(),
				resolution = SharedSettings.instance.graphics.resolution.ToTelemetry(),
				graphics_quality = SharedSettings.instance.graphics.GetLevel().ToString().ToLowerInvariant()
			};
			PlatformManager.instance.SendTelemetry("graphics_settings", payload);
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "graphics_settings");
		}
	}
```

- `private static Hardware() : System.Void`  

```csharp
private static void Hardware()
	{
		try
		{
			HardwarePayload payload = new HardwarePayload
			{
				os_version = SystemInfo.operatingSystem,
				ram = Mathf.RoundToInt((float)SystemInfo.systemMemorySize / 1024f),
				gfx_memory = Mathf.RoundToInt((float)SystemInfo.graphicsMemorySize / 1024f),
				cpucount = SystemInfo.processorCount,
				cpu_model = SystemInfo.processorType,
				gpu_model = SystemInfo.graphicsDeviceName
			};
			PlatformManager.instance.SendTelemetry("hardware", payload);
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "hardware");
		}
	}
```

- `public static InputIdleEnd() : System.Void`  

```csharp
public static void InputIdleEnd()
	{
		try
		{
			if (gameplayData != null && s_Session.active && !GameManager.instance.isGameLoading)
			{
				InputIdleEndPayload payload = new InputIdleEndPayload
				{
					playthrough_id = s_Session.guid,
					simulation_speed_start = s_Session.startSimulationSpeed,
					simulation_speed_end = gameplayData.simulationSpeed,
					duration = Math.Round(s_Session.idleTime.TotalSeconds, 2)
				};
				PlatformManager.instance.SendTelemetry("idle_time_end", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "idle_time_end");
		}
	}
```

- `public static InputIdleStart() : System.Void`  

```csharp
public static void InputIdleStart()
	{
		try
		{
			if (gameplayData != null && s_Session.active)
			{
				s_Session.ReportInputIdle();
			}
		}
		catch (Exception exception)
		{
			log.Warn(exception);
		}
	}
```

- `private static Language() : System.Void`  

```csharp
private static void Language()
	{
		try
		{
			LanguagePayload payload = new LanguagePayload
			{
				os_language = Helpers.GetSystemLanguage(),
				game_language = GameManager.instance.localizationManager.activeLocaleId
			};
			PlatformManager.instance.SendTelemetry("language", payload);
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "language");
		}
	}
```

- `public static MilestoneUnlocked(System.Int32 milestoneIndex) : System.Void`  

```csharp
public static void MilestoneUnlocked(int milestoneIndex)
	{
		try
		{
			if (gameplayData != null && s_Session.active)
			{
				MilestoneUnlockedPayload payload = new MilestoneUnlockedPayload
				{
					playthrough_id = s_Session.guid,
					milestone_index = milestoneIndex,
					ingame_days = gameplayData.GetDay()
				};
				PlatformManager.instance.SendTelemetry("milestone_unlocked", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "milestone_unlocked");
		}
	}
```

- `private static ModsUsed() : System.Void`  

```csharp
private static void ModsUsed()
	{
		try
		{
			if (AssetDatabase<ParadoxMods>.instance?.dataSource is ParadoxModsDataSource paradoxModsDataSource)
			{
				ModUsedPayload payload = new ModUsedPayload
				{
					mods = (from mod in paradoxModsDataSource.GetActiveMods()
						select new ModUsedPayload.Mod
						{
							mod_name = mod.displayName,
							mod_id = mod.id.ToString(),
							mod_tags = mod.tags
						}).ToArray()
				};
				if (payload.mods.Any())
				{
					PlatformManager.instance.SendTelemetry("mod_used", payload);
				}
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "mod_used");
		}
	}
```

- `public static OpenSession(System.Guid guid) : System.Void`  

```csharp
public static void OpenSession(Guid guid)
	{
		try
		{
			CloseSession();
			if (gameplayData != null && !s_Session.active)
			{
				s_Session.Open(guid);
				OpenSessionPayload payload = new OpenSessionPayload
				{
					playthrough_id = s_Session.guid,
					map_id = gameplayData.mapName,
					gameplay_mode = GameManager.instance.gameMode.ToTelemetry(),
					tutorial_messages = gameplayData.tutorialEnabled,
					unlimited_money = gameplayData.unlimitedMoney,
					unlock_all = gameplayData.unlockAll,
					disasters = gameplayData.naturalDisasters,
					mode_settings = gameplayData.currentGameMode
				};
				PlatformManager.instance.SendTelemetry("playsession_start", payload);
				ModsUsed();
				DlcsInstalled(gameplayData);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "playsession_start");
		}
	}
```

- `public static PanelClosed(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
public static void PanelClosed(GamePanel panel)
	{
		try
		{
			if (s_Session.active && s_Session.PanelClosed(panel.GetType().Name, out var timeSpent))
			{
				string name = panel.GetType().Name;
				PanelClosedPayload payload = new PanelClosedPayload
				{
					playthrough_id = s_Session.guid,
					panel_name = name,
					time_spent = Math.Round(timeSpent.TotalSeconds, 2)
				};
				PlatformManager.instance.SendTelemetry("panel_closed", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "panel_closed");
		}
	}
```

- `public static PanelOpened(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
public static void PanelOpened(GamePanel panel)
	{
		if (s_Session.active)
		{
			s_Session.PanelOpened(panel.GetType().Name);
		}
	}
```

- `public static PlaceBuilding(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase building, Unity.Mathematics.float3 position) : System.Void`  

```csharp
public static void PlaceBuilding(Entity entity, PrefabBase building, float3 position)
	{
		try
		{
			if (gameplayData != null && s_Session.active && (building.Has<BuildingPrefab>() || building.Has<BuildingExtensionPrefab>()))
			{
				string type = null;
				int building_level = 0;
				if (building.TryGet<UIObject>(out var component) && component.m_Group is UIAssetCategoryPrefab uIAssetCategoryPrefab)
				{
					type = uIAssetCategoryPrefab.name;
				}
				string origin = "base_game";
				if (building.TryGet<ContentPrerequisite>(out var component2))
				{
					origin = component2.m_ContentPrerequisite.name;
				}
				BuildingPlacedPayload payload = new BuildingPlacedPayload
				{
					playthrough_id = s_Session.guid,
					map_id = gameplayData.mapName,
					building_id = building.name,
					type = type,
					building_level = building_level,
					coordinates = $"{position.x}|{position.z}",
					origin = origin
				};
				PlatformManager.instance.SendTelemetry("building_placed", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "building_placed");
		}
	}
```

- `public static Policy(Game.Policies.ModifiedSystem+PolicyEventInfo eventInfo) : System.Void`  

```csharp
public static void Policy(ModifiedSystem.PolicyEventInfo eventInfo)
	{
		try
		{
			if (gameplayData != null && s_Session.active)
			{
				PolicyPrefab prefab = gameplayData.GetPrefab<PolicyPrefab>(eventInfo.m_Entity);
				if (prefab.m_Visibility != PolicyVisibility.HideFromPolicyList)
				{
					PolicyPayload payload = new PolicyPayload
					{
						playthrough_id = s_Session.guid,
						policy_id = prefab.name,
						policy_category = prefab.m_Category,
						policy_range = eventInfo.m_PolicyRange
					};
					PlatformManager.instance.SendTelemetry("policy", payload);
				}
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "policy");
		}
	}
```

- `public static TutorialEvent(Unity.Entities.Entity tutorial) : System.Void`  

```csharp
public static void TutorialEvent(Entity tutorial)
	{
		try
		{
			if (gameplayData != null && s_Session.active)
			{
				PrefabBase prefab = gameplayData.GetPrefab<PrefabBase>(tutorial);
				TutorialEventPayload payload = new TutorialEventPayload
				{
					playthrough_id = s_Session.guid,
					advice_followed = ((prefab != null) ? prefab.name : null)
				};
				PlatformManager.instance.SendTelemetry("tutorial_event", payload);
			}
		}
		catch (Exception exception)
		{
			log.WarnFormat(exception, "{0} telemetry event payload generation failed", "tutorial_event");
		}
	}
```


## Nested types

- `Game.PSI.Telemetry+HardwarePayload`  
- `Game.PSI.Telemetry+LanguagePayload`  
- `Game.PSI.Telemetry+GraphicsSettingsPayload`  
- `Game.PSI.Telemetry+AchievementPayload`  
- `Game.PSI.Telemetry+TutorialEventPayload`  
- `Game.PSI.Telemetry+MilestoneUnlockedPayload`  
- `Game.PSI.Telemetry+DevNodePurchasedPayload`  
- `Game.PSI.Telemetry+ControlInputPayload`  
- `Game.PSI.Telemetry+PanelClosedPayload`  
- `Game.PSI.Telemetry+CityStatsPayload`  
- `Game.PSI.Telemetry+ChirperPayload`  
- `Game.PSI.Telemetry+BuildingPlacedPayload`  
- `Game.PSI.Telemetry+PolicyPayload`  
- `Game.PSI.Telemetry+InputIdleEndPayload`  
- `Game.PSI.Telemetry+GameplayData`  
- `Game.PSI.Telemetry+Session`  
- `Game.PSI.Telemetry+OpenSessionPayload`  
- `Game.PSI.Telemetry+CloseSessionPayload`  
- `Game.PSI.Telemetry+ModUsedPayload`  
- `Game.PSI.Telemetry+DlcPayload`  
- `Game.PSI.Telemetry+<>c`  

