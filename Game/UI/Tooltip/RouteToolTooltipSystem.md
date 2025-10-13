# Game.UI.Tooltip.RouteToolTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

## Code

```csharp
public class RouteToolTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.RouteToolSystem m_RouteTool;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Unity.Entities.EntityQuery m_TempRouteQuery;
    private Unity.Entities.EntityQuery m_TempStopQuery;
    private Game.UI.Tooltip.NameTooltip m_StopName;
    private Game.UI.Tooltip.NameTooltip m_RouteName;

    public RouteToolTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void TryAddRouteName();
    public System.Void TryAddStopName();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteTool`  

```csharp
private Game.Tools.RouteToolSystem m_RouteTool;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Unity.Entities.EntityQuery m_TempRouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempRouteQuery;
```

- `private Unity.Entities.EntityQuery m_TempStopQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempStopQuery;
```

- `private Game.UI.Tooltip.NameTooltip m_StopName`  

```csharp
private Game.UI.Tooltip.NameTooltip m_StopName;
```

- `private Game.UI.Tooltip.NameTooltip m_RouteName`  

```csharp
private Game.UI.Tooltip.NameTooltip m_RouteName;
```


## Constructors

- `public RouteToolTooltipSystem()`  

```csharp
public RouteToolTooltipSystem();
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

- `public TryAddRouteName() : System.Void`  

```csharp
public System.Void TryAddRouteName();
```

- `public TryAddStopName() : System.Void`  

```csharp
public System.Void TryAddStopName();
```


