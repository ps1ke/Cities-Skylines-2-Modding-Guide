# Game.UI.Menu.NotificationUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationUISystem : Game.UI.UISystemBase
{
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.UI.Menu.NotificationUISystem+NotificationInfo>> m_NotificationsBinding;
    private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.NotificationUISystem+DelayedNotificationInfo> m_PendingRemoval;
    private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.NotificationUISystem+NotificationInfo> m_NotificationsMap;
    private System.Collections.Generic.Dictionary<System.Int32, Colossal.PSI.Common.Mod> m_ModInfoCache;
    private System.Boolean m_Dirty;
    private static const System.String kGroup;
    private static const System.String kInstallation;
    private static const System.String kDownloading;
    private static const System.Single kDelay;

    public static System.Int32 width { get; }

    public NotificationUISystem();

    private System.Void AddModNotification(Colossal.PSI.Common.Mod mod, System.String notificationId);
    public Game.UI.Menu.NotificationUISystem+NotificationInfo AddOrUpdateNotification(System.String identifier, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked);
    private System.String GetModNotificationId(Colossal.PSI.Common.Mod mod, System.String suffix);
    private System.String GetModNotificationId(System.String modId, System.String suffix);
    public static System.String GetText(System.String textId);
    public static System.String GetTitle(System.String titleId);
    private System.Void HandleModDownloadCompleted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod);
    private System.Void HandleModDownloadFailed(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod);
    private System.Void HandleModDownloadStarted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod);
    private System.Void HandleModInstallProgress(Colossal.PSI.Common.IModSupport psi, System.Int32 modId, Colossal.PSI.Common.TransferStatus status);
    private System.Void HandleModSubscription(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status);
    private System.Void HandleTransferOnGoing(Colossal.PSI.Common.ITransferSupport psi, Colossal.PSI.Common.TransferStatus status);
    public System.Boolean NotificationExists(System.String identifier);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ProcessPendingRemovals(System.Single deltaTime);
    public System.Void RemoveNotification(System.String identifier, System.Single delay, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked);
    private System.Void SelectNotification(System.String notificationId);
    private System.Void UpdateNotification(Game.UI.Menu.NotificationUISystem+NotificationInfo notificationInfo, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked);
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.UI.Menu.NotificationUISystem+NotificationInfo>> m_NotificationsBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.UI.Menu.NotificationUISystem+NotificationInfo>> m_NotificationsBinding;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.NotificationUISystem+DelayedNotificationInfo> m_PendingRemoval`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.NotificationUISystem+DelayedNotificationInfo> m_PendingRemoval;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.NotificationUISystem+NotificationInfo> m_NotificationsMap`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.NotificationUISystem+NotificationInfo> m_NotificationsMap;
```

- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.PSI.Common.Mod> m_ModInfoCache`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, Colossal.PSI.Common.Mod> m_ModInfoCache;
```

- `private System.Boolean m_Dirty`  

```csharp
private System.Boolean m_Dirty;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.String kInstallation`  

```csharp
private static const System.String kInstallation;
```

- `private static const System.String kDownloading`  

```csharp
private static const System.String kDownloading;
```

- `private static const System.Single kDelay`  

```csharp
private static const System.Single kDelay;
```


## Properties

- `public static System.Int32 width { get }`  

```csharp
public static System.Int32 width { get; }
```


## Constructors

- `public NotificationUISystem()`  

```csharp
[Preserve]
	public NotificationUISystem()
	{
	}
```


## Methods

- `private AddModNotification(Colossal.PSI.Common.Mod mod, System.String notificationId = null) : System.Void`  

```csharp
private void AddModNotification(Mod mod, string notificationId = null)
	{
		string identifier = notificationId ?? GetModNotificationId(mod);
		LocalizedString? title = LocalizedString.Value(mod.displayName);
		string thumbnail = $"{mod.thumbnailPath}?width={width})";
		Action onClick = mod.onClick;
		AddOrUpdateNotification(identifier, title, null, thumbnail, null, null, onClick);
	}
```

- `public AddOrUpdateNotification(System.String identifier, System.Nullable<Game.UI.Localization.LocalizedString> title = null, System.Nullable<Game.UI.Localization.LocalizedString> text = null, System.String thumbnail = null, System.Nullable<Colossal.PSI.Common.ProgressState> progressState = null, System.Nullable<System.Int32> progress = null, System.Action onClicked = null) : Game.UI.Menu.NotificationUISystem+NotificationInfo`  

```csharp
public NotificationInfo AddOrUpdateNotification(string identifier, LocalizedString? title = null, LocalizedString? text = null, string thumbnail = null, ProgressState? progressState = null, int? progress = null, Action onClicked = null)
	{
		if (m_NotificationsMap.TryGetValue(identifier, out var value))
		{
			UpdateNotification(value, title, text, thumbnail, progressState, progress, onClicked);
		}
		else
		{
			value = new NotificationInfo(identifier);
			UpdateNotification(value, title, text, thumbnail, progressState, progress, onClicked);
			m_NotificationsMap.Add(identifier, value);
			m_NotificationsBinding.value.Add(value);
		}
		m_Dirty = true;
		return value;
	}
```

- `private GetModNotificationId(Colossal.PSI.Common.Mod mod, System.String suffix = null) : System.String`  

```csharp
private string GetModNotificationId(string modId, string suffix = null)
	{
		if (!string.IsNullOrEmpty(suffix))
		{
			return modId + "." + suffix;
		}
		return modId;
	}
```

- `private GetModNotificationId(System.String modId, System.String suffix = null) : System.String`  

```csharp
private string GetModNotificationId(string modId, string suffix = null)
	{
		if (!string.IsNullOrEmpty(suffix))
		{
			return modId + "." + suffix;
		}
		return modId;
	}
```

- `public static GetText(System.String textId) : System.String`  

```csharp
public static string GetText(string textId)
	{
		return "Menu.NOTIFICATION_DESCRIPTION[" + textId + "]";
	}
```

- `public static GetTitle(System.String titleId) : System.String`  

```csharp
public static string GetTitle(string titleId)
	{
		return "Menu.NOTIFICATION_TITLE[" + titleId + "]";
	}
```

- `private HandleModDownloadCompleted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private void HandleModDownloadCompleted(IModSupport psi, Mod mod)
	{
		m_ModInfoCache.Remove(mod.id);
		string modNotificationId = GetModNotificationId(mod, "installation");
		LocalizedString? text = GetText("InstallComplete");
		ProgressState? progressState = ProgressState.Complete;
		int? progress = 100;
		RemoveNotification(modNotificationId, 2f, null, text, null, progressState, progress);
	}
```

- `private HandleModDownloadFailed(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private void HandleModDownloadFailed(IModSupport psi, Mod mod)
	{
		m_ModInfoCache.Remove(mod.id);
		string modNotificationId = GetModNotificationId(mod, "installation");
		LocalizedString? text = GetText("InstallFailed");
		ProgressState? progressState = ProgressState.Failed;
		int? progress = 100;
		RemoveNotification(modNotificationId, 2f, null, text, null, progressState, progress);
	}
```

- `private HandleModDownloadStarted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private void HandleModDownloadStarted(IModSupport psi, Mod mod)
	{
		m_ModInfoCache[mod.id] = mod;
		AddModNotification(mod, GetModNotificationId(mod, "installation"));
		string modNotificationId = GetModNotificationId(mod, "installation");
		LocalizedString? text = GetText("DownloadPending");
		int? progress = 0;
		AddOrUpdateNotification(modNotificationId, null, text, null, null, progress);
	}
```

- `private HandleModInstallProgress(Colossal.PSI.Common.IModSupport psi, System.Int32 modId, Colossal.PSI.Common.TransferStatus status) : System.Void`  

```csharp
private void HandleModInstallProgress(IModSupport psi, int modId, TransferStatus status)
	{
		ProgressState progressState = ((status.type != TransferType.Install) ? ProgressState.Progressing : status.progressState);
		string modNotificationId = GetModNotificationId(status.id, "installation");
		LocalizedString? text = GetText($"{TransferType.Install}{progressState}");
		ProgressState? progressState2 = progressState;
		int? progress = Mathf.CeilToInt(status.progress * 100f);
		AddOrUpdateNotification(modNotificationId, null, text, null, progressState2, progress);
		if (status.type != TransferType.Download)
		{
			return;
		}
		if (status.progressState == ProgressState.Progressing && !NotificationExists(GetModNotificationId(status.id, "downloading")))
		{
			if (!m_ModInfoCache.TryGetValue(modId, out var value))
			{
				value = new Mod
				{
					id = modId
				};
			}
			AddModNotification(value, GetModNotificationId(value, "downloading"));
		}
		else if (status.progressState == ProgressState.Complete && NotificationExists(GetModNotificationId(status.id, "downloading")))
		{
			string modNotificationId2 = GetModNotificationId(status.id, "downloading");
			text = GetText("DownloadComplete");
			progressState2 = ProgressState.Complete;
			progress = 100;
			RemoveNotification(modNotificationId2, 2f, null, text, null, progressState2, progress);
		}
	}
```

- `private HandleModSubscription(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status) : System.Void`  

```csharp
private void HandleModSubscription(IModSupport psi, Mod mod, ModSubscriptionStatus status)
	{
		string text = status.ToString();
		string modNotificationId = GetModNotificationId(mod, text);
		LocalizedString? title = LocalizedString.Value(mod.displayName);
		LocalizedString? text2 = GetText(text);
		string thumbnail = $"{mod.thumbnailPath}?width={width})";
		Action onClick = mod.onClick;
		RemoveNotification(modNotificationId, 2f, title, text2, thumbnail, null, null, onClick);
	}
```

- `private HandleTransferOnGoing(Colossal.PSI.Common.ITransferSupport psi, Colossal.PSI.Common.TransferStatus status) : System.Void`  

```csharp
private void HandleTransferOnGoing(ITransferSupport psi, TransferStatus status)
	{
		if (NotificationExists(GetModNotificationId(status.id, "downloading")))
		{
			if (status.progressState == ProgressState.Complete)
			{
				string modNotificationId = GetModNotificationId(status.id, "downloading");
				LocalizedString? text = GetText("DownloadComplete");
				ProgressState? progressState = ProgressState.Complete;
				int? progress = 100;
				RemoveNotification(modNotificationId, 2f, null, text, null, progressState, progress);
			}
			else if (status.progressState == ProgressState.Failed)
			{
				string modNotificationId2 = GetModNotificationId(status.id, "downloading");
				LocalizedString? text = GetText("DownloadFailed");
				ProgressState? progressState = ProgressState.Failed;
				int? progress = 100;
				RemoveNotification(modNotificationId2, 2f, null, text, null, progressState, progress);
			}
			else
			{
				string modNotificationId3 = GetModNotificationId(status.id, "downloading");
				LocalizedString? text = GetText("DownloadProgressing");
				ProgressState? progressState = status.progressState;
				int? progress = Mathf.CeilToInt(status.progress * 100f);
				AddOrUpdateNotification(modNotificationId3, null, text, null, progressState, progress);
			}
		}
	}
```

- `public NotificationExists(System.String identifier) : System.Boolean`  

```csharp
public bool NotificationExists(string identifier)
	{
		return m_NotificationsMap.ContainsKey(identifier);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		NotificationSystem.BindUI(this);
		base.OnCreate();
		m_NotificationsMap = new Dictionary<string, NotificationInfo>();
		m_PendingRemoval = new Dictionary<string, DelayedNotificationInfo>();
		m_ModInfoCache = new Dictionary<int, Mod>();
		AddBinding(m_NotificationsBinding = new ValueBinding<List<NotificationInfo>>("notification", "notifications", new List<NotificationInfo>(), new ListWriter<NotificationInfo>(new ValueWriter<NotificationInfo>())));
		AddBinding(new TriggerBinding<string>("notification", "selectNotification", SelectNotification));
		PlatformManager.instance.onModSubscriptionChanged += HandleModSubscription;
		PlatformManager.instance.onModDownloadStarted += HandleModDownloadStarted;
		PlatformManager.instance.onModDownloadCompleted += HandleModDownloadCompleted;
		PlatformManager.instance.onModDownloadFailed += HandleModDownloadFailed;
		PlatformManager.instance.onModInstallProgress += HandleModInstallProgress;
		PlatformManager.instance.onTransferOnGoing += HandleTransferOnGoing;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		NotificationSystem.UnbindUI();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		ProcessPendingRemovals(base.CheckedStateRef.WorldUnmanaged.Time.DeltaTime);
		if (m_Dirty)
		{
			m_Dirty = false;
			m_NotificationsBinding.TriggerUpdate();
		}
	}
```

- `private ProcessPendingRemovals(System.Single deltaTime) : System.Void`  

```csharp
private void ProcessPendingRemovals(float deltaTime)
	{
		List<NotificationInfo> list = null;
		foreach (KeyValuePair<string, DelayedNotificationInfo> item in m_PendingRemoval)
		{
			if (item.Value.Update(deltaTime, out var notification))
			{
				list = new List<NotificationInfo> { notification };
				m_Dirty = true;
			}
		}
		if (list == null)
		{
			return;
		}
		foreach (NotificationInfo item2 in list)
		{
			m_NotificationsBinding.value.Remove(item2);
			m_NotificationsMap.Remove(item2.id);
			m_PendingRemoval.Remove(item2.id);
		}
	}
```

- `public RemoveNotification(System.String identifier, System.Single delay = 0, System.Nullable<Game.UI.Localization.LocalizedString> title = null, System.Nullable<Game.UI.Localization.LocalizedString> text = null, System.String thumbnail = null, System.Nullable<Colossal.PSI.Common.ProgressState> progressState = null, System.Nullable<System.Int32> progress = null, System.Action onClicked = null) : System.Void`  

```csharp
public void RemoveNotification(string identifier, float delay = 0f, LocalizedString? title = null, LocalizedString? text = null, string thumbnail = null, ProgressState? progressState = null, int? progress = null, Action onClicked = null)
	{
		NotificationInfo notificationInfo = AddOrUpdateNotification(identifier, title, text, thumbnail, progressState, progress, onClicked);
		DelayedNotificationInfo value;
		if (delay == 0f)
		{
			m_NotificationsBinding.value.Remove(notificationInfo);
			m_NotificationsMap.Remove(notificationInfo.id);
		}
		else if (m_PendingRemoval.TryGetValue(identifier, out value))
		{
			value.Reset(delay);
		}
		else
		{
			m_PendingRemoval.Add(identifier, new DelayedNotificationInfo(notificationInfo, delay));
		}
		m_Dirty = true;
	}
```

- `private SelectNotification(System.String notificationId) : System.Void`  

```csharp
private void SelectNotification(string notificationId)
	{
		if (m_NotificationsMap.TryGetValue(notificationId, out var value))
		{
			value.onClicked?.Invoke();
		}
	}
```

- `private UpdateNotification(Game.UI.Menu.NotificationUISystem+NotificationInfo notificationInfo, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked) : System.Void`  

```csharp
private void UpdateNotification(NotificationInfo notificationInfo, LocalizedString? title, LocalizedString? text, string thumbnail, ProgressState? progressState, int? progress, Action onClicked)
	{
		if (title.HasValue && !notificationInfo.title.HasValue)
		{
			notificationInfo.title = title;
		}
		if (text.HasValue)
		{
			notificationInfo.text = text;
		}
		if (thumbnail != null && notificationInfo.thumbnail == null)
		{
			notificationInfo.thumbnail = thumbnail;
		}
		if (progressState.HasValue)
		{
			notificationInfo.progressState = progressState.Value;
		}
		if (progress.HasValue)
		{
			notificationInfo.progress = progress.Value;
		}
		if (onClicked != null && notificationInfo.onClicked == null)
		{
			notificationInfo.onClicked = onClicked;
		}
	}
```


## Nested types

- `Game.UI.Menu.NotificationUISystem+DelayedNotificationInfo`  
- `Game.UI.Menu.NotificationUISystem+NotificationInfo`  

