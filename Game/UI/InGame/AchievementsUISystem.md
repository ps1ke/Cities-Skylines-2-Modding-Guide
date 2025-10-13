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
[Preserve]
	public AchievementsUISystem()
	{
	}
```


## Methods

- `private BindAchievement(Colossal.UI.Binding.IJsonWriter binder, Colossal.PSI.Common.IAchievement achievement) : System.Void`  

```csharp
private void BindAchievement(IJsonWriter binder, IAchievement achievement)
	{
		binder.TypeBegin("achievements.Achievement");
		binder.PropertyName("localeKey");
		binder.Write(achievement.internalName);
		bool flag = !achievement.achieved;
		binder.PropertyName("imagePath");
		binder.Write(GetImagePath(achievement, flag));
		binder.PropertyName("locked");
		binder.Write(flag);
		binder.PropertyName("isIncremental");
		binder.Write(achievement.isIncremental);
		binder.PropertyName("progress");
		binder.Write(achievement.progress);
		binder.PropertyName("maxProgress");
		binder.Write(achievement.maxProgress);
		binder.PropertyName("dlcImage");
		binder.Write(GetDlcImage(achievement.dlcId));
		binder.PropertyName("isDevelopment");
		binder.Write(achievement is DevelopmentAchievementsManager.DevelopmentAchievement);
		binder.TypeEnd();
	}
```

- `private BindAchievements(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindAchievements(IJsonWriter binder)
	{
		int num = PlatformManager.instance.CountAchievements();
		m_TabStatusBinding.Update();
		if (num > 0)
		{
			binder.ArrayBegin(num);
			foreach (IAchievement item in PlatformManager.instance.EnumerateAchievements())
			{
				BindAchievement(binder, item);
			}
			binder.ArrayEnd();
		}
		else
		{
			binder.ArrayBegin(0u);
			binder.ArrayEnd();
		}
	}
```

- `private GetAchievementTabStatus() : System.Int32`  

```csharp
private int GetAchievementTabStatus()
	{
		if (PlatformManager.instance.CountAchievements() == 0)
		{
			return 1;
		}
		if (m_CityConfigurationSystem.usedMods.Count > 0)
		{
			return 2;
		}
		if (!PlatformManager.instance.achievementsEnabled)
		{
			return 3;
		}
		return 0;
	}
```

- `private static GetDlcImage(Colossal.PSI.Common.DlcId dlcId) : System.String`  

```csharp
private static string GetDlcImage(DlcId dlcId)
	{
		if (!(dlcId != DlcId.BaseGame))
		{
			return null;
		}
		return "Media/DLC/" + PlatformManager.instance.GetDlcName(dlcId) + ".svg";
	}
```

- `private static GetImagePath(Colossal.PSI.Common.IAchievement achievement, System.Boolean locked) : System.String`  

```csharp
private static string GetImagePath(IAchievement achievement, bool locked)
	{
		return "Media/Game/Achievements/" + achievement.internalName + (locked ? "_locked" : "") + ".png";
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		PlatformManager.instance.onAchievementUpdated += UpdateAchievements;
		AddBinding(m_AchievementsBinding = new RawValueBinding("achievements", "achievements", BindAchievements));
		AddBinding(m_TabStatusBinding = new GetterValueBinding<int>("achievements", "achievementTabStatus", GetAchievementTabStatus));
	}
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGameLoadingComplete(Purpose purpose, GameMode mode)
	{
		m_TabStatusBinding.Update();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
	}
```

- `private UpdateAchievements(Colossal.PSI.Common.IAchievementsSupport backend, Colossal.PSI.Common.AchievementId id) : System.Void`  

```csharp
private void UpdateAchievements(IAchievementsSupport backend, AchievementId id)
	{
		m_AchievementsBinding.Update();
	}
```


## Nested types

- `Game.UI.InGame.AchievementsUISystem+AchievementTabStatus`  

