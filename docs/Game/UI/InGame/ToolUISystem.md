# Game.UI.InGame.ToolUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.NetToolSystem m_NetToolSystem`  
- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  
- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  
- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Tools.TerrainToolSystem m_TerrainToolSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  
- `private Game.Tools.BulldozeToolSystem m_BulldozeToolSystem`  
- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_BulldozeQuery`  
- `private Unity.Entities.EntityQuery m_BrushQuery`  
- `private Colossal.UI.Binding.RawValueBinding m_ActiveToolBinding`  
- `private System.Collections.Generic.List<Game.Tools.ToolMode> m_ToolModes`  
- `public static const System.String kGroup`  

## Constructors

- `public ToolUISystem()`  

## Methods

- `private <OnCreate>b__18_0() : System.UInt32`  
- `private <OnCreate>b__18_1() : System.UInt32`  
- `private <OnCreate>b__18_10() : System.Boolean`  
- `private <OnCreate>b__18_11() : System.Single`  
- `private <OnCreate>b__18_12() : System.Single`  
- `private <OnCreate>b__18_13() : Unity.Entities.Entity`  
- `private <OnCreate>b__18_14() : System.Single`  
- `private <OnCreate>b__18_15() : System.Nullable<System.Single>`  
- `private <OnCreate>b__18_16() : System.Single`  
- `private <OnCreate>b__18_17() : System.Single`  
- `private <OnCreate>b__18_19() : System.Single`  
- `private <OnCreate>b__18_2() : System.UInt32`  
- `private <OnCreate>b__18_20() : System.Single`  
- `private <OnCreate>b__18_21() : System.Single`  
- `private <OnCreate>b__18_3() : UnityEngine.Color32`  
- `private <OnCreate>b__18_4() : System.Single`  
- `private <OnCreate>b__18_5() : System.Single`  
- `private <OnCreate>b__18_6() : System.Boolean`  
- `private <OnCreate>b__18_7() : System.Single`  
- `private <OnCreate>b__18_8() : System.Boolean`  
- `private <OnCreate>b__18_9() : System.Boolean`  
- `private AllowBrush() : System.Boolean`  
- `private BindActiveTool(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindBrushTypes() : Game.UI.InGame.ToolUISystem+Brush[]`  
- `private BindToolModes(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private GetColorSupported() : System.Boolean`  
- `private GetElevationDownDisabled() : System.Boolean`  
- `private GetElevationRange() : Colossal.Mathematics.Bounds1`  
- `private GetElevationUpDisabled() : System.Boolean`  
- `private GetParallelModeSupported() : System.Boolean`  
- `private GetToolSystem(System.String tool) : Game.Tools.ToolBaseSystem`  
- `private InitSnapOptionNames() : System.String[]`  
- `private IsEditor() : System.Boolean`  
- `private OnBulldozeConfirmationRequested() : System.Void`  
- `private OnConfirmBulldoze(System.Int32 msg) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnElevationDown() : System.Void`  
- `private OnElevationScroll() : System.Void`  
- `private OnElevationUp() : System.Void`  
- `private OnPrefabChanged(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  
- `private SelectBrush(Unity.Entities.Entity entity) : System.Void`  
- `private SelectTool(System.String tool) : System.Void`  
- `public SelectTool(Game.Tools.ToolBaseSystem tool) : System.Void`  
- `private SelectToolMode(System.Int32 modeIndex) : System.Void`  
- `private SetBrushAngle(System.Single angle) : System.Void`  
- `private SetBrushHeight(System.Single height) : System.Void`  
- `private SetBrushSize(System.Single size) : System.Void`  
- `private SetBrushStrength(System.Single strength) : System.Void`  
- `private SetColor(UnityEngine.Color32 color) : System.Void`  
- `private SetDistance(System.Single distance) : System.Void`  
- `private SetElevationStep(System.Single step) : System.Void`  
- `private SetParallelOffset(System.Single offset) : System.Void`  
- `private SetSelectedSnapMask(System.UInt32 mask) : System.Void`  
- `private SetUndergroundMode(System.Boolean enabled) : System.Void`  
- `private ToggleParallelMode() : System.Void`  

## Nested types

- `Game.UI.InGame.ToolUISystem+Brush`  
- `Game.UI.InGame.ToolUISystem+<>c`  

