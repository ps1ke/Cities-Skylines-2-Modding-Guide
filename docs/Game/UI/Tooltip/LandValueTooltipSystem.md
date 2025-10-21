# Game.UI.Tooltip.LandValueTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LandValueTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Common.RaycastSystem m_RaycastSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.TerrainToolSystem m_TerrainToolSystem;
    private Game.Simulation.LandValueSystem m_LandValueSystem;
    private Game.Debug.LandValueDebugSystem m_LandValueDebugSystem;
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Unity.Entities.EntityQuery m_AttractivenessParameterQuery;
    private Unity.Entities.EntityQuery m_LandValueParameterQuery;
    private Game.UI.Tooltip.FloatTooltip m_LandValueTooltip;
    private Game.UI.Tooltip.FloatTooltip m_TerrainAttractiveTooltip;
    private Game.UI.Tooltip.FloatTooltip m_AirPollutionTooltip;
    private Game.UI.Tooltip.FloatTooltip m_GroundPollutionTooltip;
    private Game.UI.Tooltip.FloatTooltip m_NoisePollutionTooltip;
    private Colossal.Collections.NativeValue<System.Single> m_LandValueResult;
    private Colossal.Collections.NativeValue<System.Single> m_TerrainAttractiveResult;
    private Colossal.Collections.NativeValue<System.Single> m_AirPollutionResult;
    private Colossal.Collections.NativeValue<System.Single> m_NoisePollutionResult;
    private Colossal.Collections.NativeValue<System.Single> m_GroundPollutionResult;

    public LandValueTooltipSystem();

    private System.Boolean IsInfomodeActivated();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.RaycastSystem m_RaycastSystem`  

```csharp
private Game.Common.RaycastSystem m_RaycastSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.TerrainToolSystem m_TerrainToolSystem`  

```csharp
private Game.Tools.TerrainToolSystem m_TerrainToolSystem;
```

- `private Game.Simulation.LandValueSystem m_LandValueSystem`  

```csharp
private Game.Simulation.LandValueSystem m_LandValueSystem;
```

- `private Game.Debug.LandValueDebugSystem m_LandValueDebugSystem`  

```csharp
private Game.Debug.LandValueDebugSystem m_LandValueDebugSystem;
```

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Unity.Entities.EntityQuery m_AttractivenessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_AttractivenessParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueParameterQuery;
```

- `private Game.UI.Tooltip.FloatTooltip m_LandValueTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_LandValueTooltip;
```

- `private Game.UI.Tooltip.FloatTooltip m_TerrainAttractiveTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_TerrainAttractiveTooltip;
```

- `private Game.UI.Tooltip.FloatTooltip m_AirPollutionTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_AirPollutionTooltip;
```

- `private Game.UI.Tooltip.FloatTooltip m_GroundPollutionTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_GroundPollutionTooltip;
```

- `private Game.UI.Tooltip.FloatTooltip m_NoisePollutionTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_NoisePollutionTooltip;
```

- `private Colossal.Collections.NativeValue<System.Single> m_LandValueResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_LandValueResult;
```

- `private Colossal.Collections.NativeValue<System.Single> m_TerrainAttractiveResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_TerrainAttractiveResult;
```

- `private Colossal.Collections.NativeValue<System.Single> m_AirPollutionResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_AirPollutionResult;
```

- `private Colossal.Collections.NativeValue<System.Single> m_NoisePollutionResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_NoisePollutionResult;
```

- `private Colossal.Collections.NativeValue<System.Single> m_GroundPollutionResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_GroundPollutionResult;
```


## Constructors

- `public LandValueTooltipSystem()`  

```csharp
public LandValueTooltipSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.UI.Tooltip.LandValueTooltipSystem+LandValueTooltipJob`  

