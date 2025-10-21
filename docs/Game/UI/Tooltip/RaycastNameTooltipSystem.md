# Game.UI.Tooltip.RaycastNameTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RaycastNameTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.UI.NameSystem m_NameSystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.UI.Tooltip.NameTooltip m_Tooltip;

    public RaycastNameTooltipSystem();

    private System.Void AdjustTargets(Unity.Entities.Entity& instance, Unity.Entities.Entity& prefab);
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

- `private Game.UI.Tooltip.NameTooltip m_Tooltip`  

```csharp
private Game.UI.Tooltip.NameTooltip m_Tooltip;
```


## Constructors

- `public RaycastNameTooltipSystem()`  

```csharp
public RaycastNameTooltipSystem();
```


## Methods

- `private AdjustTargets(Unity.Entities.Entity& instance, Unity.Entities.Entity& prefab) : System.Void`  

```csharp
private System.Void AdjustTargets(Unity.Entities.Entity& instance, Unity.Entities.Entity& prefab);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


