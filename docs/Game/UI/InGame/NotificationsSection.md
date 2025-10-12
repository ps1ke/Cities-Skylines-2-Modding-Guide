# Game.UI.InGame.NotificationsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> <notifications>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> m_NotificationsResult`  
- `private Unity.Collections.NativeArray<System.Boolean> m_DisplayResult`  
- `private Game.UI.InGame.NotificationsSection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `protected System.Boolean displayForOutsideConnections { protected get }`  
- `protected System.Boolean displayForUnderConstruction { protected get }`  
- `protected System.Boolean displayForUpgrades { protected get }`  
- `private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> notifications { private get; private set }`  

## Constructors

- `public NotificationsSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetNotifications(Unity.Entities.EntityManager EntityManager, Unity.Entities.Entity entity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications) : Unity.Collections.NativeList<Game.UI.InGame.Notification>`  
- `public static GetNotifications(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefDataFromEntity, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBufferFromEntity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications) : Unity.Collections.NativeList<Game.UI.InGame.Notification>`  
- `public static HasNotifications(Unity.Entities.Entity entity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBuffer, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

## Nested types

- `Game.UI.InGame.NotificationsSection+CheckAndCacheNotificationsJob`  
- `Game.UI.InGame.NotificationsSection+CheckAndCacheVisitorNotificationsJob`  
- `Game.UI.InGame.NotificationsSection+TypeHandle`  

