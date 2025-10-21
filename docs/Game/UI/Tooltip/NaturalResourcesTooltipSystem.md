# Game.UI.Tooltip.NaturalResourcesTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

## Code

```csharp
public class NaturalResourcesTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Common.RaycastSystem m_RaycastSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
    private Game.UI.Tooltip.IntTooltip m_Fertility;
    private Game.UI.Tooltip.IntTooltip m_Wood;
    private Game.UI.Tooltip.IntTooltip m_Oil;
    private Game.UI.Tooltip.IntTooltip m_Ore;
    private Game.UI.Tooltip.IntTooltip m_Fish;
    private Game.Common.RaycastResult m_RaycastResult;

    private Game.Common.RaycastResult raycastResult { private get; private set; }

    public NaturalResourcesTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Common.RaycastSystem m_RaycastSystem`  

```csharp
private Game.Common.RaycastSystem m_RaycastSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_ActiveInfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Fertility`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Fertility;
```

- `private Game.UI.Tooltip.IntTooltip m_Wood`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Wood;
```

- `private Game.UI.Tooltip.IntTooltip m_Oil`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Oil;
```

- `private Game.UI.Tooltip.IntTooltip m_Ore`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Ore;
```

- `private Game.UI.Tooltip.IntTooltip m_Fish`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Fish;
```

- `private Game.Common.RaycastResult m_RaycastResult`  

```csharp
private Game.Common.RaycastResult m_RaycastResult;
```


## Properties

- `private Game.Common.RaycastResult raycastResult { private get; private set }`  

```csharp
private Game.Common.RaycastResult raycastResult { private get; private set; }
```


## Constructors

- `public NaturalResourcesTooltipSystem()`  

```csharp
public NaturalResourcesTooltipSystem();
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


