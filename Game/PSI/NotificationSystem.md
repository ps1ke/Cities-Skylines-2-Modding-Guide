# Game.PSI.NotificationSystem

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NotificationSystem
{
    private static Game.UI.Menu.NotificationUISystem s_System;

    public static System.Void BindUI(Game.UI.Menu.NotificationUISystem value);
    public static System.Boolean Exist(System.String identifier);
    public static System.Void Pop(System.String identifier, System.Single delay, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String titleId, System.String textId, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked);
    public static System.Void Push(System.String identifier, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String titleId, System.String textId, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked);
    public static System.Void UnbindUI();
}
```


## Fields

- `private static Game.UI.Menu.NotificationUISystem s_System`  

```csharp
private static Game.UI.Menu.NotificationUISystem s_System;
```


## Methods

- `public static BindUI(Game.UI.Menu.NotificationUISystem value) : System.Void`  

```csharp
public static void BindUI(NotificationUISystem value)
	{
		s_System = value;
	}
```

- `public static Exist(System.String identifier) : System.Boolean`  

```csharp
public static bool Exist(string identifier)
	{
		return s_System?.NotificationExists(identifier) ?? false;
	}
```

- `public static Pop(System.String identifier, System.Single delay = 0, System.Nullable<Game.UI.Localization.LocalizedString> title = null, System.Nullable<Game.UI.Localization.LocalizedString> text = null, System.String titleId = null, System.String textId = null, System.String thumbnail = null, System.Nullable<Colossal.PSI.Common.ProgressState> progressState = null, System.Nullable<System.Int32> progress = null, System.Action onClicked = null) : System.Void`  

```csharp
public static void Pop(string identifier, float delay = 0f, LocalizedString? title = null, LocalizedString? text = null, string titleId = null, string textId = null, string thumbnail = null, ProgressState? progressState = null, int? progress = null, Action onClicked = null)
	{
		s_System?.RemoveNotification(identifier, delay, title ?? ((LocalizedString)NotificationUISystem.GetTitle(titleId)), text ?? ((LocalizedString)NotificationUISystem.GetText(textId)), thumbnail, progressState, progress, onClicked);
	}
```

- `public static Push(System.String identifier, System.Nullable<Game.UI.Localization.LocalizedString> title = null, System.Nullable<Game.UI.Localization.LocalizedString> text = null, System.String titleId = null, System.String textId = null, System.String thumbnail = null, System.Nullable<Colossal.PSI.Common.ProgressState> progressState = null, System.Nullable<System.Int32> progress = null, System.Action onClicked = null) : System.Void`  

```csharp
public static void Push(string identifier, LocalizedString? title = null, LocalizedString? text = null, string titleId = null, string textId = null, string thumbnail = null, ProgressState? progressState = null, int? progress = null, Action onClicked = null)
	{
		s_System?.AddOrUpdateNotification(identifier, title ?? ((LocalizedString)NotificationUISystem.GetTitle(titleId)), text ?? ((LocalizedString)NotificationUISystem.GetText(textId)), thumbnail, progressState, progress, onClicked);
	}
```

- `public static UnbindUI() : System.Void`  

```csharp
public static void UnbindUI()
	{
		s_System = null;
	}
```


