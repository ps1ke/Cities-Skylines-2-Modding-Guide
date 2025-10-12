# Game.UI.InGame.AchievementsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Colossal.UI.Binding.RawValueBinding m_AchievementsBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TabStatusBinding`  
- `private static const System.String kGroup`  

## Constructors

- `public AchievementsUISystem()`  

## Methods

- `private BindAchievement(Colossal.UI.Binding.IJsonWriter binder, Colossal.PSI.Common.IAchievement achievement) : System.Void`  
- `private BindAchievements(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private GetAchievementTabStatus() : System.Int32`  
- `private static GetDlcImage(Colossal.PSI.Common.DlcId dlcId) : System.String`  
- `private static GetImagePath(Colossal.PSI.Common.IAchievement achievement, System.Boolean locked) : System.String`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UpdateAchievements(Colossal.PSI.Common.IAchievementsSupport backend, Colossal.PSI.Common.AchievementId id) : System.Void`  

## Nested types

- `Game.UI.InGame.AchievementsUISystem+AchievementTabStatus`  

