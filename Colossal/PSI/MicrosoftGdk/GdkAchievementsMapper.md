# Colossal.PSI.MicrosoftGdk.GdkAchievementsMapper

**Assembly:** `Colossal.PSI.MicrosoftGdk`  
**Namespace:** `Colossal.PSI.MicrosoftGdk`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsMapper<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData>`  

## Code

```csharp
public abstract class GdkAchievementsMapper : Colossal.PSI.Common.IAchievementsMapper<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData>
{
    private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData> m_Mapping;

    public System.Int32 count { get; }

    protected GdkAchievementsMapper();

    public System.Boolean Lookup(Colossal.PSI.Common.AchievementId achievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData& value);
    protected System.Void Map(Colossal.PSI.Common.AchievementId achievementId, System.Int32 backendId, System.Int32 unlocksAtOverride);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData> m_Mapping`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData> m_Mapping;
```


## Properties

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```


## Constructors

- `protected GdkAchievementsMapper()`  

```csharp
protected GdkAchievementsMapper();
```


## Methods

- `public Lookup(Colossal.PSI.Common.AchievementId achievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData& value) : System.Boolean`  

```csharp
public System.Boolean Lookup(Colossal.PSI.Common.AchievementId achievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData& value);
```

- `protected Map(Colossal.PSI.Common.AchievementId achievementId, System.Int32 backendId, System.Int32 unlocksAtOverride = -1) : System.Void`  

```csharp
protected System.Void Map(Colossal.PSI.Common.AchievementId achievementId, System.Int32 backendId, System.Int32 unlocksAtOverride);
```


