# Game.UI.InGame.AchievementsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class AchievementsUISystem : Game.UI.UISystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Colossal.UI.Binding.RawValueBinding m_AchievementsBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TabStatusBinding;
    private static const System.String kGroup;

    public AchievementsUISystem();

    private System.Void BindAchievement(Colossal.UI.Binding.IJsonWriter binder, Colossal.PSI.Common.IAchievement achievement);
    private System.Void BindAchievements(Colossal.UI.Binding.IJsonWriter binder);
    private System.Int32 GetAchievementTabStatus();
    private static System.String GetDlcImage(Colossal.PSI.Common.DlcId dlcId);
    private static System.String GetImagePath(Colossal.PSI.Common.IAchievement achievement, System.Boolean locked);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    private System.Void UpdateAchievements(Colossal.PSI.Common.IAchievementsSupport backend, Colossal.PSI.Common.AchievementId id);
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Colossal.UI.Binding.RawValueBinding m_AchievementsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_AchievementsBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TabStatusBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TabStatusBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public AchievementsUISystem()`  

```csharp
public AchievementsUISystem();
```


## Methods

- `private BindAchievement(Colossal.UI.Binding.IJsonWriter binder, Colossal.PSI.Common.IAchievement achievement) : System.Void`  

```csharp
private System.Void BindAchievement(Colossal.UI.Binding.IJsonWriter binder, Colossal.PSI.Common.IAchievement achievement);
```

- `private BindAchievements(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindAchievements(Colossal.UI.Binding.IJsonWriter binder);
```

- `private GetAchievementTabStatus() : System.Int32`  

```csharp
private System.Int32 GetAchievementTabStatus();
```

- `private static GetDlcImage(Colossal.PSI.Common.DlcId dlcId) : System.String`  

```csharp
private static System.String GetDlcImage(Colossal.PSI.Common.DlcId dlcId);
```

- `private static GetImagePath(Colossal.PSI.Common.IAchievement achievement, System.Boolean locked) : System.String`  

```csharp
private static System.String GetImagePath(Colossal.PSI.Common.IAchievement achievement, System.Boolean locked);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private UpdateAchievements(Colossal.PSI.Common.IAchievementsSupport backend, Colossal.PSI.Common.AchievementId id) : System.Void`  

```csharp
private System.Void UpdateAchievements(Colossal.PSI.Common.IAchievementsSupport backend, Colossal.PSI.Common.AchievementId id);
```


## Nested types

- `Game.UI.InGame.AchievementsUISystem+AchievementTabStatus`  

