# Game.UI.Tooltip.CityPolicyTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityPolicyTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Common.RaycastSystem m_RaycastSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
    private Unity.Entities.Entity m_AdvancedPollutionManagementPolicy;
    private Game.UI.Tooltip.StringTooltip m_PollutionManagement;
    private Game.Common.RaycastResult m_RaycastResult;

    private Game.Common.RaycastResult raycastResult { private get; private set; }

    public CityPolicyTooltipSystem();

    private System.Boolean IsAdvancedPollutionManagementEnabled();
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

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_ActiveInfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
```

- `private Unity.Entities.Entity m_AdvancedPollutionManagementPolicy`  

```csharp
private Unity.Entities.Entity m_AdvancedPollutionManagementPolicy;
```

- `private Game.UI.Tooltip.StringTooltip m_PollutionManagement`  

```csharp
private Game.UI.Tooltip.StringTooltip m_PollutionManagement;
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

- `public CityPolicyTooltipSystem()`  

```csharp
public CityPolicyTooltipSystem();
```


## Methods

- `private IsAdvancedPollutionManagementEnabled() : System.Boolean`  

```csharp
private System.Boolean IsAdvancedPollutionManagementEnabled();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


