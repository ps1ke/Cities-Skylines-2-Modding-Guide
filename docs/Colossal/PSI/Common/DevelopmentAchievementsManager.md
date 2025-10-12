# Colossal.PSI.Common.DevelopmentAchievementsManager

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Fields

- `private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated`  
- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement> m_AchievementsMap`  
- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  
- `private static Colossal.Logging.ILog log`  
- `private static System.Byte[] sBuffer`  

## Properties

- `public System.String name { get }`  
- `public System.Boolean isInitialized { get }`  

## Constructors

- `public DevelopmentAchievementsManager()`  

## Methods

- `public ClearAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  
- `private CompareProgress(System.Int32 currentProgress, System.Int32 newProgress, Colossal.PSI.Common.IndicateType type) : System.Boolean`  
- `public CountAchievements(System.Boolean onlyAchieved = False) : System.Int32`  
- `public Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public EnumerateAchievements() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement>`  
- `public GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement) : System.Boolean`  
- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type) : System.Void`  
- `private IndicateAchievementProgress(Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement meta, System.Int32 value, Colossal.PSI.Common.IndicateType type) : System.Void`  
- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementsID, System.Int32 step = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  
- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public LogVersion(System.Text.StringBuilder b) : System.Void`  
- `public ResetAchievements() : System.Void`  
- `public UnlockAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  
- `private UnlockAchievement(Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement meta) : System.Void`  
- `public Update() : System.Void`  

## Events

- `onAchievementUpdated` : `Colossal.PSI.Common.AchievementUpdatedEventHandler`  
- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

## Nested types

- `Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement`  
- `Colossal.PSI.Common.DevelopmentAchievementsManager+<>c`  

