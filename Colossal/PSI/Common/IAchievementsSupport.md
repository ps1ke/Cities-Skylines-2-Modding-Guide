# Colossal.PSI.Common.IAchievementsSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IAchievementsSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public abstract System.Void ClearAchievement(Colossal.PSI.Common.AchievementId achievementID);
    public abstract System.Int32 CountAchievements(System.Boolean onlyAchieved);
    public abstract System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement> EnumerateAchievements();
    public abstract System.Boolean GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement);
    public abstract System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementId, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    public abstract System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    public abstract System.Threading.Tasks.Task LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
    public abstract System.Void ResetAchievements();
    public abstract System.Void UnlockAchievement(Colossal.PSI.Common.AchievementId achievementId);
}
```


## Methods

- `public abstract ClearAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  

```csharp
public abstract System.Void ClearAchievement(Colossal.PSI.Common.AchievementId achievementID);
```

- `public abstract CountAchievements(System.Boolean onlyAchieved = False) : System.Int32`  

```csharp
public abstract System.Int32 CountAchievements(System.Boolean onlyAchieved);
```

- `public abstract EnumerateAchievements() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement> EnumerateAchievements();
```

- `public abstract GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement) : System.Boolean`  

```csharp
public abstract System.Boolean GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement);
```

- `public abstract IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementId, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  

```csharp
public abstract System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementId, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `public abstract IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  

```csharp
public abstract System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `public abstract LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
```

- `public abstract ResetAchievements() : System.Void`  

```csharp
public abstract System.Void ResetAchievements();
```

- `public abstract UnlockAchievement(Colossal.PSI.Common.AchievementId achievementId) : System.Void`  

```csharp
public abstract System.Void UnlockAchievement(Colossal.PSI.Common.AchievementId achievementId);
```


## Events

- `onAchievementUpdated` : `Colossal.PSI.Common.AchievementUpdatedEventHandler`  

```csharp
public event Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
```


