# Game.UI.Tooltip.TempNotificationTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempNotificationTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Notifications.IconPriority> m_Priorities;
    private Unity.Collections.NativeList<Game.UI.Tooltip.TempNotificationTooltipSystem+ItemInfo> m_Items;
    private System.Collections.Generic.List<Game.UI.Tooltip.StringTooltip> m_Tooltips;
    private Game.UI.Tooltip.TempNotificationTooltipSystem+TypeHandle __TypeHandle;

    public TempNotificationTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean HasIcon(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.Notifications.IconPriority minPriority);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Notifications.IconPriority> m_Priorities`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Notifications.IconPriority> m_Priorities;
```

- `private Unity.Collections.NativeList<Game.UI.Tooltip.TempNotificationTooltipSystem+ItemInfo> m_Items`  

```csharp
private Unity.Collections.NativeList<Game.UI.Tooltip.TempNotificationTooltipSystem+ItemInfo> m_Items;
```

- `private System.Collections.Generic.List<Game.UI.Tooltip.StringTooltip> m_Tooltips`  

```csharp
private System.Collections.Generic.List<Game.UI.Tooltip.StringTooltip> m_Tooltips;
```

- `private Game.UI.Tooltip.TempNotificationTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempNotificationTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempNotificationTooltipSystem()`  

```csharp
public TempNotificationTooltipSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private HasIcon(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.Notifications.IconPriority minPriority) : System.Boolean`  

```csharp
private System.Boolean HasIcon(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.Notifications.IconPriority minPriority);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.UI.Tooltip.TempNotificationTooltipSystem+ItemInfo`  
- `Game.UI.Tooltip.TempNotificationTooltipSystem+TypeHandle`  

