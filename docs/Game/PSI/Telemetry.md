# Game.PSI.Telemetry

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Telemetry`  

## Fields

- `private static Colossal.Logging.ILog log`  
- `private static Game.PSI.Telemetry+GameplayData <gameplayData>k__BackingField`  
- `private static Game.PSI.Telemetry+Session s_Session`  
- `private static const System.String kHardwareEvent`  
- `private static const System.String kLanguageEvent`  
- `private static const System.String kGraphicsSettings`  
- `private static const System.String kAchievementUnlocked`  
- `private static const System.String kTutorialEvent`  
- `private static const System.String kMilestoneUnlocked`  
- `private static const System.String kDevNodePurchased`  
- `private static const System.String kControlInput`  
- `private static const System.String kPanelClosed`  
- `private static const System.String kCityStats`  
- `private static const System.String kChirper`  
- `private static const System.String kBuildingPlaced`  
- `private static const System.String kPolicy`  
- `private static const System.String kInputIdleEnd`  
- `private static const System.String kSessionOpen`  
- `private static const System.String kSessionClose`  
- `private static const System.String kModsUsed`  
- `private static const System.String kDlc`  

## Properties

- `public static Game.PSI.Telemetry+GameplayData gameplayData { get; set }`  

## Methods

- `public static AchievementUnlocked(Colossal.PSI.Common.AchievementId id) : System.Void`  
- `public static Chirp(Unity.Entities.Entity chirpPrefab, System.UInt32 likes) : System.Void`  
- `public static CityStats() : System.Void`  
- `public static CloseSession() : System.Void`  
- `public static ControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  
- `public static DevNodePurchased(Game.Prefabs.DevTreeNodePrefab nodePrefab) : System.Void`  
- `private static DlcsInstalled(Game.PSI.Telemetry+GameplayData data) : System.Void`  
- `public static FireSessionStartEvents() : System.Void`  
- `public static GetCurrentSession() : System.Guid`  
- `public static GraphicsSettings() : System.Void`  
- `private static Hardware() : System.Void`  
- `public static InputIdleEnd() : System.Void`  
- `public static InputIdleStart() : System.Void`  
- `private static Language() : System.Void`  
- `public static MilestoneUnlocked(System.Int32 milestoneIndex) : System.Void`  
- `private static ModsUsed() : System.Void`  
- `public static OpenSession(System.Guid guid) : System.Void`  
- `public static PanelClosed(Game.UI.InGame.GamePanel panel) : System.Void`  
- `public static PanelOpened(Game.UI.InGame.GamePanel panel) : System.Void`  
- `public static PlaceBuilding(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase building, Unity.Mathematics.float3 position) : System.Void`  
- `public static Policy(Game.Policies.ModifiedSystem+PolicyEventInfo eventInfo) : System.Void`  
- `public static TutorialEvent(Unity.Entities.Entity tutorial) : System.Void`  

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

