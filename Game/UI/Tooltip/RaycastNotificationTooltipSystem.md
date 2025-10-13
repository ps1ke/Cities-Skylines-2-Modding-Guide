# Game.UI.Tooltip.RaycastNotificationTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RaycastNotificationTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Game.UI.Tooltip.NotificationTooltip m_Tooltip;

    public RaycastNotificationTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Game.UI.Tooltip.NotificationTooltip m_Tooltip`  

```csharp
private Game.UI.Tooltip.NotificationTooltip m_Tooltip;
```


## Constructors

- `public RaycastNotificationTooltipSystem()`  

```csharp
public RaycastNotificationTooltipSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


