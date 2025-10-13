# Game.Notifications.NotificationsUtils

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NotificationsUtils
{
    public static const System.Single ICON_VISIBLE_THROUGH_DISTANCE;

    public static Game.Notifications.IconLayerMask GetIconLayerMask(Game.Notifications.IconClusterLayer layer);
}
```


## Fields

- `public static const System.Single ICON_VISIBLE_THROUGH_DISTANCE`  

```csharp
public static const System.Single ICON_VISIBLE_THROUGH_DISTANCE;
```


## Methods

- `public static GetIconLayerMask(Game.Notifications.IconClusterLayer layer) : Game.Notifications.IconLayerMask`  

```csharp
public static IconLayerMask GetIconLayerMask(IconClusterLayer layer)
	{
		return (IconLayerMask)(1 << (int)layer);
	}
```


