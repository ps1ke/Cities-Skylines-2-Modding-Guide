# Game.UI.InGame.ToolUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class ToolUISystem : Game.UI.UISystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
    private Game.Tools.RouteToolSystem m_RouteToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.TerrainToolSystem m_TerrainToolSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
    private Game.Tools.BulldozeToolSystem m_BulldozeToolSystem;
    private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_BulldozeQuery;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Colossal.UI.Binding.RawValueBinding m_ActiveToolBinding;
    private System.Collections.Generic.List<Game.Tools.ToolMode> m_ToolModes;
    public static const System.String kGroup;

    public ToolUISystem();

    private System.UInt32 <OnCreate>b__18_0();
    private System.UInt32 <OnCreate>b__18_1();
    private System.Boolean <OnCreate>b__18_10();
    private System.Single <OnCreate>b__18_11();
    private System.Single <OnCreate>b__18_12();
    private Unity.Entities.Entity <OnCreate>b__18_13();
    private System.Single <OnCreate>b__18_14();
    private System.Nullable<System.Single> <OnCreate>b__18_15();
    private System.Single <OnCreate>b__18_16();
    private System.Single <OnCreate>b__18_17();
    private System.Single <OnCreate>b__18_19();
    private System.UInt32 <OnCreate>b__18_2();
    private System.Single <OnCreate>b__18_20();
    private System.Single <OnCreate>b__18_21();
    private UnityEngine.Color32 <OnCreate>b__18_3();
    private System.Single <OnCreate>b__18_4();
    private System.Single <OnCreate>b__18_5();
    private System.Boolean <OnCreate>b__18_6();
    private System.Single <OnCreate>b__18_7();
    private System.Boolean <OnCreate>b__18_8();
    private System.Boolean <OnCreate>b__18_9();
    private System.Boolean AllowBrush();
    private System.Void BindActiveTool(Colossal.UI.Binding.IJsonWriter binder);
    private Game.UI.InGame.ToolUISystem+Brush[] BindBrushTypes();
    private System.Void BindToolModes(Colossal.UI.Binding.IJsonWriter binder);
    private System.Boolean GetColorSupported();
    private System.Boolean GetElevationDownDisabled();
    private Colossal.Mathematics.Bounds1 GetElevationRange();
    private System.Boolean GetElevationUpDisabled();
    private System.Boolean GetParallelModeSupported();
    private Game.Tools.ToolBaseSystem GetToolSystem(System.String tool);
    private System.String[] InitSnapOptionNames();
    private System.Boolean IsEditor();
    private System.Void OnBulldozeConfirmationRequested();
    private System.Void OnConfirmBulldoze(System.Int32 msg);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    private System.Void OnElevationDown();
    private System.Void OnElevationScroll();
    private System.Void OnElevationUp();
    private System.Void OnPrefabChanged(Game.Prefabs.PrefabBase prefab);
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    private System.Void SelectBrush(Unity.Entities.Entity entity);
    private System.Void SelectTool(System.String tool);
    public System.Void SelectTool(Game.Tools.ToolBaseSystem tool);
    private System.Void SelectToolMode(System.Int32 modeIndex);
    private System.Void SetBrushAngle(System.Single angle);
    private System.Void SetBrushHeight(System.Single height);
    private System.Void SetBrushSize(System.Single size);
    private System.Void SetBrushStrength(System.Single strength);
    private System.Void SetColor(UnityEngine.Color32 color);
    private System.Void SetDistance(System.Single distance);
    private System.Void SetElevationStep(System.Single step);
    private System.Void SetParallelOffset(System.Single offset);
    private System.Void SetSelectedSnapMask(System.UInt32 mask);
    private System.Void SetUndergroundMode(System.Boolean enabled);
    private System.Void ToggleParallelMode();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  

```csharp
private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  

```csharp
private Game.Tools.RouteToolSystem m_RouteToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.TerrainToolSystem m_TerrainToolSystem`  

```csharp
private Game.Tools.TerrainToolSystem m_TerrainToolSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  

```csharp
private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
```

- `private Game.Tools.BulldozeToolSystem m_BulldozeToolSystem`  

```csharp
private Game.Tools.BulldozeToolSystem m_BulldozeToolSystem;
```

- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  

```csharp
private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_BulldozeQuery`  

```csharp
private Unity.Entities.EntityQuery m_BulldozeQuery;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_ActiveToolBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ActiveToolBinding;
```

- `private System.Collections.Generic.List<Game.Tools.ToolMode> m_ToolModes`  

```csharp
private System.Collections.Generic.List<Game.Tools.ToolMode> m_ToolModes;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Constructors

- `public ToolUISystem()`  

```csharp
public ToolUISystem();
```


## Methods

- `private <OnCreate>b__18_0() : System.UInt32`  

```csharp
private System.UInt32 <OnCreate>b__18_0();
```

- `private <OnCreate>b__18_1() : System.UInt32`  

```csharp
private System.UInt32 <OnCreate>b__18_1();
```

- `private <OnCreate>b__18_10() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__18_10();
```

- `private <OnCreate>b__18_11() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_11();
```

- `private <OnCreate>b__18_12() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_12();
```

- `private <OnCreate>b__18_13() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__18_13();
```

- `private <OnCreate>b__18_14() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_14();
```

- `private <OnCreate>b__18_15() : System.Nullable<System.Single>`  

```csharp
private System.Nullable<System.Single> <OnCreate>b__18_15();
```

- `private <OnCreate>b__18_16() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_16();
```

- `private <OnCreate>b__18_17() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_17();
```

- `private <OnCreate>b__18_19() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_19();
```

- `private <OnCreate>b__18_2() : System.UInt32`  

```csharp
private System.UInt32 <OnCreate>b__18_2();
```

- `private <OnCreate>b__18_20() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_20();
```

- `private <OnCreate>b__18_21() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_21();
```

- `private <OnCreate>b__18_3() : UnityEngine.Color32`  

```csharp
private UnityEngine.Color32 <OnCreate>b__18_3();
```

- `private <OnCreate>b__18_4() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_4();
```

- `private <OnCreate>b__18_5() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_5();
```

- `private <OnCreate>b__18_6() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__18_6();
```

- `private <OnCreate>b__18_7() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_7();
```

- `private <OnCreate>b__18_8() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__18_8();
```

- `private <OnCreate>b__18_9() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__18_9();
```

- `private AllowBrush() : System.Boolean`  

```csharp
private System.Boolean AllowBrush();
```

- `private BindActiveTool(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindActiveTool(Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindBrushTypes() : Game.UI.InGame.ToolUISystem+Brush[]`  

```csharp
private Game.UI.InGame.ToolUISystem+Brush[] BindBrushTypes();
```

- `private BindToolModes(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindToolModes(Colossal.UI.Binding.IJsonWriter binder);
```

- `private GetColorSupported() : System.Boolean`  

```csharp
private System.Boolean GetColorSupported();
```

- `private GetElevationDownDisabled() : System.Boolean`  

```csharp
private System.Boolean GetElevationDownDisabled();
```

- `private GetElevationRange() : Colossal.Mathematics.Bounds1`  

```csharp
private Colossal.Mathematics.Bounds1 GetElevationRange();
```

- `private GetElevationUpDisabled() : System.Boolean`  

```csharp
private System.Boolean GetElevationUpDisabled();
```

- `private GetParallelModeSupported() : System.Boolean`  

```csharp
private System.Boolean GetParallelModeSupported();
```

- `private GetToolSystem(System.String tool) : Game.Tools.ToolBaseSystem`  

```csharp
private Game.Tools.ToolBaseSystem GetToolSystem(System.String tool);
```

- `private InitSnapOptionNames() : System.String[]`  

```csharp
private System.String[] InitSnapOptionNames();
```

- `private IsEditor() : System.Boolean`  

```csharp
private System.Boolean IsEditor();
```

- `private OnBulldozeConfirmationRequested() : System.Void`  

```csharp
private System.Void OnBulldozeConfirmationRequested();
```

- `private OnConfirmBulldoze(System.Int32 msg) : System.Void`  

```csharp
private System.Void OnConfirmBulldoze(System.Int32 msg);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `private OnElevationDown() : System.Void`  

```csharp
private System.Void OnElevationDown();
```

- `private OnElevationScroll() : System.Void`  

```csharp
private System.Void OnElevationScroll();
```

- `private OnElevationUp() : System.Void`  

```csharp
private System.Void OnElevationUp();
```

- `private OnPrefabChanged(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void OnPrefabChanged(Game.Prefabs.PrefabBase prefab);
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
```

- `private SelectBrush(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void SelectBrush(Unity.Entities.Entity entity);
```

- `private SelectTool(System.String tool) : System.Void`  

```csharp
private System.Void SelectTool(System.String tool);
```

- `public SelectTool(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
public System.Void SelectTool(Game.Tools.ToolBaseSystem tool);
```

- `private SelectToolMode(System.Int32 modeIndex) : System.Void`  

```csharp
private System.Void SelectToolMode(System.Int32 modeIndex);
```

- `private SetBrushAngle(System.Single angle) : System.Void`  

```csharp
private System.Void SetBrushAngle(System.Single angle);
```

- `private SetBrushHeight(System.Single height) : System.Void`  

```csharp
private System.Void SetBrushHeight(System.Single height);
```

- `private SetBrushSize(System.Single size) : System.Void`  

```csharp
private System.Void SetBrushSize(System.Single size);
```

- `private SetBrushStrength(System.Single strength) : System.Void`  

```csharp
private System.Void SetBrushStrength(System.Single strength);
```

- `private SetColor(UnityEngine.Color32 color) : System.Void`  

```csharp
private System.Void SetColor(UnityEngine.Color32 color);
```

- `private SetDistance(System.Single distance) : System.Void`  

```csharp
private System.Void SetDistance(System.Single distance);
```

- `private SetElevationStep(System.Single step) : System.Void`  

```csharp
private System.Void SetElevationStep(System.Single step);
```

- `private SetParallelOffset(System.Single offset) : System.Void`  

```csharp
private System.Void SetParallelOffset(System.Single offset);
```

- `private SetSelectedSnapMask(System.UInt32 mask) : System.Void`  

```csharp
private System.Void SetSelectedSnapMask(System.UInt32 mask);
```

- `private SetUndergroundMode(System.Boolean enabled) : System.Void`  

```csharp
private System.Void SetUndergroundMode(System.Boolean enabled);
```

- `private ToggleParallelMode() : System.Void`  

```csharp
private System.Void ToggleParallelMode();
```


## Nested types

- `Game.UI.InGame.ToolUISystem+Brush`  
- `Game.UI.InGame.ToolUISystem+<>c`  

