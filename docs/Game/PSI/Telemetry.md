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
public static System.Void AchievementUnlocked(Colossal.PSI.Common.AchievementId id);
```

- `public static Chirp(Unity.Entities.Entity chirpPrefab, System.UInt32 likes) : System.Void`  

```csharp
public static System.Void Chirp(Unity.Entities.Entity chirpPrefab, System.UInt32 likes);
```

- `public static CityStats() : System.Void`  

```csharp
public static System.Void CityStats();
```

- `public static CloseSession() : System.Void`  

```csharp
public static System.Void CloseSession();
```

- `public static ControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  

```csharp
public static System.Void ControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme);
```

- `public static DevNodePurchased(Game.Prefabs.DevTreeNodePrefab nodePrefab) : System.Void`  

```csharp
public static System.Void DevNodePurchased(Game.Prefabs.DevTreeNodePrefab nodePrefab);
```

- `private static DlcsInstalled(Game.PSI.Telemetry+GameplayData data) : System.Void`  

```csharp
private static System.Void DlcsInstalled(Game.PSI.Telemetry+GameplayData data);
```

- `public static FireSessionStartEvents() : System.Void`  

```csharp
public static System.Void FireSessionStartEvents();
```

- `public static GetCurrentSession() : System.Guid`  

```csharp
public static System.Guid GetCurrentSession();
```

- `public static GraphicsSettings() : System.Void`  

```csharp
public static System.Void GraphicsSettings();
```

- `private static Hardware() : System.Void`  

```csharp
private static System.Void Hardware();
```

- `public static InputIdleEnd() : System.Void`  

```csharp
public static System.Void InputIdleEnd();
```

- `public static InputIdleStart() : System.Void`  

```csharp
public static System.Void InputIdleStart();
```

- `private static Language() : System.Void`  

```csharp
private static System.Void Language();
```

- `public static MilestoneUnlocked(System.Int32 milestoneIndex) : System.Void`  

```csharp
public static System.Void MilestoneUnlocked(System.Int32 milestoneIndex);
```

- `private static ModsUsed() : System.Void`  

```csharp
private static System.Void ModsUsed();
```

- `public static OpenSession(System.Guid guid) : System.Void`  

```csharp
public static System.Void OpenSession(System.Guid guid);
```

- `public static PanelClosed(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
public static System.Void PanelClosed(Game.UI.InGame.GamePanel panel);
```

- `public static PanelOpened(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
public static System.Void PanelOpened(Game.UI.InGame.GamePanel panel);
```

- `public static PlaceBuilding(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase building, Unity.Mathematics.float3 position) : System.Void`  

```csharp
public static System.Void PlaceBuilding(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase building, Unity.Mathematics.float3 position);
```

- `public static Policy(Game.Policies.ModifiedSystem+PolicyEventInfo eventInfo) : System.Void`  

```csharp
public static System.Void Policy(Game.Policies.ModifiedSystem+PolicyEventInfo eventInfo);
```

- `public static TutorialEvent(Unity.Entities.Entity tutorial) : System.Void`  

```csharp
public static System.Void TutorialEvent(Unity.Entities.Entity tutorial);
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

