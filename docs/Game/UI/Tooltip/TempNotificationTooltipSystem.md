# Game.UI.Tooltip.TempNotificationTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Notifications.IconPriority> m_Priorities`  
- `private Unity.Collections.NativeList<Game.UI.Tooltip.TempNotificationTooltipSystem+ItemInfo> m_Items`  
- `private System.Collections.Generic.List<Game.UI.Tooltip.StringTooltip> m_Tooltips`  
- `private Game.UI.Tooltip.TempNotificationTooltipSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TempNotificationTooltipSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private HasIcon(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.Notifications.IconPriority minPriority) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.UI.Tooltip.TempNotificationTooltipSystem+ItemInfo`  
- `Game.UI.Tooltip.TempNotificationTooltipSystem+TypeHandle`  

