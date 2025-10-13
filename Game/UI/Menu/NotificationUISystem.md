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
public NotificationUISystem();
```


## Methods

- `private AddModNotification(Colossal.PSI.Common.Mod mod, System.String notificationId = null) : System.Void`  

```csharp
private System.Void AddModNotification(Colossal.PSI.Common.Mod mod, System.String notificationId);
```

- `public AddOrUpdateNotification(System.String identifier, System.Nullable<Game.UI.Localization.LocalizedString> title = null, System.Nullable<Game.UI.Localization.LocalizedString> text = null, System.String thumbnail = null, System.Nullable<Colossal.PSI.Common.ProgressState> progressState = null, System.Nullable<System.Int32> progress = null, System.Action onClicked = null) : Game.UI.Menu.NotificationUISystem+NotificationInfo`  

```csharp
public Game.UI.Menu.NotificationUISystem+NotificationInfo AddOrUpdateNotification(System.String identifier, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked);
```

- `private GetModNotificationId(Colossal.PSI.Common.Mod mod, System.String suffix = null) : System.String`  

```csharp
private System.String GetModNotificationId(Colossal.PSI.Common.Mod mod, System.String suffix);
```

- `private GetModNotificationId(System.String modId, System.String suffix = null) : System.String`  

```csharp
private System.String GetModNotificationId(System.String modId, System.String suffix);
```

- `public static GetText(System.String textId) : System.String`  

```csharp
public static System.String GetText(System.String textId);
```

- `public static GetTitle(System.String titleId) : System.String`  

```csharp
public static System.String GetTitle(System.String titleId);
```

- `private HandleModDownloadCompleted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private System.Void HandleModDownloadCompleted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod);
```

- `private HandleModDownloadFailed(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private System.Void HandleModDownloadFailed(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod);
```

- `private HandleModDownloadStarted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private System.Void HandleModDownloadStarted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod);
```

- `private HandleModInstallProgress(Colossal.PSI.Common.IModSupport psi, System.Int32 modId, Colossal.PSI.Common.TransferStatus status) : System.Void`  

```csharp
private System.Void HandleModInstallProgress(Colossal.PSI.Common.IModSupport psi, System.Int32 modId, Colossal.PSI.Common.TransferStatus status);
```

- `private HandleModSubscription(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status) : System.Void`  

```csharp
private System.Void HandleModSubscription(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status);
```

- `private HandleTransferOnGoing(Colossal.PSI.Common.ITransferSupport psi, Colossal.PSI.Common.TransferStatus status) : System.Void`  

```csharp
private System.Void HandleTransferOnGoing(Colossal.PSI.Common.ITransferSupport psi, Colossal.PSI.Common.TransferStatus status);
```

- `public NotificationExists(System.String identifier) : System.Boolean`  

```csharp
public System.Boolean NotificationExists(System.String identifier);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ProcessPendingRemovals(System.Single deltaTime) : System.Void`  

```csharp
private System.Void ProcessPendingRemovals(System.Single deltaTime);
```

- `public RemoveNotification(System.String identifier, System.Single delay = 0, System.Nullable<Game.UI.Localization.LocalizedString> title = null, System.Nullable<Game.UI.Localization.LocalizedString> text = null, System.String thumbnail = null, System.Nullable<Colossal.PSI.Common.ProgressState> progressState = null, System.Nullable<System.Int32> progress = null, System.Action onClicked = null) : System.Void`  

```csharp
public System.Void RemoveNotification(System.String identifier, System.Single delay, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked);
```

- `private SelectNotification(System.String notificationId) : System.Void`  

```csharp
private System.Void SelectNotification(System.String notificationId);
```

- `private UpdateNotification(Game.UI.Menu.NotificationUISystem+NotificationInfo notificationInfo, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked) : System.Void`  

```csharp
private System.Void UpdateNotification(Game.UI.Menu.NotificationUISystem+NotificationInfo notificationInfo, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked);
```


## Nested types

- `Game.UI.Menu.NotificationUISystem+DelayedNotificationInfo`  
- `Game.UI.Menu.NotificationUISystem+NotificationInfo`  

