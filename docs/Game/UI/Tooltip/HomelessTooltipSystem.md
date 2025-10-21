# Game.UI.Tooltip.HomelessTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HomelessTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.UI.Tooltip.IntTooltip m_HomelessCountTooltip;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_ConfigQuery;

    public HomelessTooltipSystem();

    private System.Boolean IsInfomodeActivated();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.UI.Tooltip.IntTooltip m_HomelessCountTooltip`  

```csharp
private Game.UI.Tooltip.IntTooltip m_HomelessCountTooltip;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```


## Constructors

- `public HomelessTooltipSystem()`  

```csharp
public HomelessTooltipSystem();
```


## Methods

- `private IsInfomodeActivated() : System.Boolean`  

```csharp
private System.Boolean IsInfomodeActivated();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


