# Game.UI.Menu.NotificationUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.UI.Menu.NotificationUISystem+NotificationInfo>> m_NotificationsBinding`  
- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.NotificationUISystem+DelayedNotificationInfo> m_PendingRemoval`  
- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.NotificationUISystem+NotificationInfo> m_NotificationsMap`  
- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.PSI.Common.Mod> m_ModInfoCache`  
- `private System.Boolean m_Dirty`  
- `private static const System.String kGroup`  
- `private static const System.String kInstallation`  
- `private static const System.String kDownloading`  
- `private static const System.Single kDelay`  

## Properties

- `public static System.Int32 width { get }`  

## Constructors

- `public NotificationUISystem()`  

## Methods

- `private AddModNotification(Colossal.PSI.Common.Mod mod, System.String notificationId = null) : System.Void`  
- `public AddOrUpdateNotification(System.String identifier, System.Nullable<Game.UI.Localization.LocalizedString> title = null, System.Nullable<Game.UI.Localization.LocalizedString> text = null, System.String thumbnail = null, System.Nullable<Colossal.PSI.Common.ProgressState> progressState = null, System.Nullable<System.Int32> progress = null, System.Action onClicked = null) : Game.UI.Menu.NotificationUISystem+NotificationInfo`  
- `private GetModNotificationId(Colossal.PSI.Common.Mod mod, System.String suffix = null) : System.String`  
- `private GetModNotificationId(System.String modId, System.String suffix = null) : System.String`  
- `public static GetText(System.String textId) : System.String`  
- `public static GetTitle(System.String titleId) : System.String`  
- `private HandleModDownloadCompleted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  
- `private HandleModDownloadFailed(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  
- `private HandleModDownloadStarted(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  
- `private HandleModInstallProgress(Colossal.PSI.Common.IModSupport psi, System.Int32 modId, Colossal.PSI.Common.TransferStatus status) : System.Void`  
- `private HandleModSubscription(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status) : System.Void`  
- `private HandleTransferOnGoing(Colossal.PSI.Common.ITransferSupport psi, Colossal.PSI.Common.TransferStatus status) : System.Void`  
- `public NotificationExists(System.String identifier) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ProcessPendingRemovals(System.Single deltaTime) : System.Void`  
- `public RemoveNotification(System.String identifier, System.Single delay = 0, System.Nullable<Game.UI.Localization.LocalizedString> title = null, System.Nullable<Game.UI.Localization.LocalizedString> text = null, System.String thumbnail = null, System.Nullable<Colossal.PSI.Common.ProgressState> progressState = null, System.Nullable<System.Int32> progress = null, System.Action onClicked = null) : System.Void`  
- `private SelectNotification(System.String notificationId) : System.Void`  
- `private UpdateNotification(Game.UI.Menu.NotificationUISystem+NotificationInfo notificationInfo, System.Nullable<Game.UI.Localization.LocalizedString> title, System.Nullable<Game.UI.Localization.LocalizedString> text, System.String thumbnail, System.Nullable<Colossal.PSI.Common.ProgressState> progressState, System.Nullable<System.Int32> progress, System.Action onClicked) : System.Void`  

## Nested types

- `Game.UI.Menu.NotificationUISystem+DelayedNotificationInfo`  
- `Game.UI.Menu.NotificationUISystem+NotificationInfo`  

