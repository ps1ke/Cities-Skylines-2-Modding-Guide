# Game.UI.Tooltip.AreaToolTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaToolTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.AreaToolSystem m_AreaTool;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Game.UI.Tooltip.IntTooltip m_Resources;
    private Game.UI.Tooltip.IntTooltip m_AreaSizeToolTip;
    private Game.UI.Tooltip.IntTooltip m_Storage;
    private Game.UI.Tooltip.AreaToolTooltipSystem+TypeHandle __TypeHandle;

    public AreaToolTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private static System.Boolean ShouldShowResources(Game.Tools.AreaToolSystem+Tooltip tooltip);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaTool`  

```csharp
private Game.Tools.AreaToolSystem m_AreaTool;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Resources`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Resources;
```

- `private Game.UI.Tooltip.IntTooltip m_AreaSizeToolTip`  

```csharp
private Game.UI.Tooltip.IntTooltip m_AreaSizeToolTip;
```

- `private Game.UI.Tooltip.IntTooltip m_Storage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Storage;
```

- `private Game.UI.Tooltip.AreaToolTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.AreaToolTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaToolTooltipSystem()`  

```csharp
public AreaToolTooltipSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private static ShouldShowResources(Game.Tools.AreaToolSystem+Tooltip tooltip) : System.Boolean`  

```csharp
private static System.Boolean ShouldShowResources(Game.Tools.AreaToolSystem+Tooltip tooltip);
```


## Nested types

- `Game.UI.Tooltip.AreaToolTooltipSystem+TypeHandle`  

