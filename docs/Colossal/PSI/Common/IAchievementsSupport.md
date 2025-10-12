# Colossal.PSI.Common.IAchievementsSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Methods

- `public abstract ClearAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  
- `public abstract CountAchievements(System.Boolean onlyAchieved = False) : System.Int32`  
- `public abstract EnumerateAchievements() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement>`  
- `public abstract GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement) : System.Boolean`  
- `public abstract IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementId, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  
- `public abstract IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  
- `public abstract LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public abstract ResetAchievements() : System.Void`  
- `public abstract UnlockAchievement(Colossal.PSI.Common.AchievementId achievementId) : System.Void`  

## Events

- `onAchievementUpdated` : `Colossal.PSI.Common.AchievementUpdatedEventHandler`  

