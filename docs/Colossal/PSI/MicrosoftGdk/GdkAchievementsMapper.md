# Colossal.PSI.MicrosoftGdk.GdkAchievementsMapper

**Assembly:** `Colossal.PSI.MicrosoftGdk`  
**Namespace:** `Colossal.PSI.MicrosoftGdk`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsMapper<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData>`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData> m_Mapping`  

## Properties

- `public System.Int32 count { get }`  

## Constructors

- `protected GdkAchievementsMapper()`  

## Methods

- `public Lookup(Colossal.PSI.Common.AchievementId achievementId, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData& value) : System.Boolean`  
- `protected Map(Colossal.PSI.Common.AchievementId achievementId, System.Int32 backendId, System.Int32 unlocksAtOverride = -1) : System.Void`  

