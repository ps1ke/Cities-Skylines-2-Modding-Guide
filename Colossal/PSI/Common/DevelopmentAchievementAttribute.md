# Colossal.PSI.Common.DevelopmentAchievementAttribute

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `Colossal.PSI.Common.AchievementAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class DevelopmentAchievementAttribute : Colossal.PSI.Common.AchievementAttribute
{
    public System.Boolean isDevelopment { get; }

    public DevelopmentAchievementAttribute(System.Int32 id, System.Int32 dlcId, System.Int32 unlocksAt);

}
```


## Properties

- `public System.Boolean isDevelopment { get }`  

```csharp
public System.Boolean isDevelopment { get; }
```


## Constructors

- `public DevelopmentAchievementAttribute(System.Int32 id, System.Int32 dlcId, System.Int32 unlocksAt = -1)`  

```csharp
public DevelopmentAchievementAttribute(System.Int32 id, System.Int32 dlcId, System.Int32 unlocksAt);
```


