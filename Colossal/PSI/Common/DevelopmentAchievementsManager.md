# Colossal.PSI.Common.DevelopmentAchievementsManager

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public class DevelopmentAchievementsManager : Colossal.PSI.Common.IAchievementsSupport, Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
    private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement> m_AchievementsMap;
    private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
    private static Colossal.Logging.ILog log;
    private static System.Byte[] sBuffer;

    public System.String name { get; }
    public System.Boolean isInitialized { get; }

    public DevelopmentAchievementsManager();

    public System.Void ClearAchievement(Colossal.PSI.Common.AchievementId achievementID);
    private System.Boolean CompareProgress(System.Int32 currentProgress, System.Int32 newProgress, Colossal.PSI.Common.IndicateType type);
    public System.Int32 CountAchievements(System.Boolean onlyAchieved);
    public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
    public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement> EnumerateAchievements();
    public System.Boolean GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement);
    public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    private System.Void IndicateAchievementProgress(Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement meta, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementsID, System.Int32 step, Colossal.PSI.Common.IndicateType type);
    public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
    public System.Void LogVersion(System.Text.StringBuilder b);
    public System.Void ResetAchievements();
    public System.Void UnlockAchievement(Colossal.PSI.Common.AchievementId achievementID);
    private System.Void UnlockAchievement(Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement meta);
    public System.Void Update();
}
```


## Fields

- `private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated`  

```csharp
private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
```

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement> m_AchievementsMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement> m_AchievementsMap;
```

- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  

```csharp
private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static System.Byte[] sBuffer`  

```csharp
private static System.Byte[] sBuffer;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean isInitialized { get }`  

```csharp
public System.Boolean isInitialized { get; }
```


## Constructors

- `public DevelopmentAchievementsManager()`  

```csharp
public DevelopmentAchievementsManager();
```


## Methods

- `public ClearAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  

```csharp
public System.Void ClearAchievement(Colossal.PSI.Common.AchievementId achievementID);
```

- `private CompareProgress(System.Int32 currentProgress, System.Int32 newProgress, Colossal.PSI.Common.IndicateType type) : System.Boolean`  

```csharp
private System.Boolean CompareProgress(System.Int32 currentProgress, System.Int32 newProgress, Colossal.PSI.Common.IndicateType type);
```

- `public CountAchievements(System.Boolean onlyAchieved = False) : System.Int32`  

```csharp
public System.Int32 CountAchievements(System.Boolean onlyAchieved);
```

- `public Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
```

- `public EnumerateAchievements() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement> EnumerateAchievements();
```

- `public GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement) : System.Boolean`  

```csharp
public System.Boolean GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement);
```

- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type) : System.Void`  

```csharp
public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `private IndicateAchievementProgress(Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement meta, System.Int32 value, Colossal.PSI.Common.IndicateType type) : System.Void`  

```csharp
private System.Void IndicateAchievementProgress(Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement meta, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementsID, System.Int32 step = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  

```csharp
public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementsID, System.Int32 step, Colossal.PSI.Common.IndicateType type);
```

- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
```

- `public LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
```

- `public LogVersion(System.Text.StringBuilder b) : System.Void`  

```csharp
public System.Void LogVersion(System.Text.StringBuilder b);
```

- `public ResetAchievements() : System.Void`  

```csharp
public System.Void ResetAchievements();
```

- `public UnlockAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  

```csharp
public System.Void UnlockAchievement(Colossal.PSI.Common.AchievementId achievementID);
```

- `private UnlockAchievement(Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement meta) : System.Void`  

```csharp
private System.Void UnlockAchievement(Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement meta);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


## Events

- `onAchievementUpdated` : `Colossal.PSI.Common.AchievementUpdatedEventHandler`  

```csharp
public event Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
```

- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```


## Nested types

- `Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement`  
- `Colossal.PSI.Common.DevelopmentAchievementsManager+<>c`  

