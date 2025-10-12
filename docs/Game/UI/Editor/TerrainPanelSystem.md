# Game.UI.Editor.TerrainPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup`  
- `private Game.UI.Widgets.IconButtonGroup m_MaterialButtonGroup`  
- `private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs`  
- `private static readonly System.String kHeightmapFolder`  

## Constructors

- `public TerrainPanelSystem()`  

## Methods

- `private <OnCreate>b__8_0() : System.Double`  
- `private <OnCreate>b__8_1(System.Double val) : System.Void`  
- `private <OnCreate>b__8_2() : System.Boolean`  
- `private <OnCreate>b__8_3() : System.Boolean`  
- `private DisplayHeightmapError() : System.Void`  
- `private static GetHeightmaps() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  
- `protected virtual OnCancel() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnLoadHeightmap(Colossal.Hash128 guid) : System.Void`  
- `private OnLoadWorldHeightmap(Colossal.Hash128 guid) : System.Void`  
- `private OnSaveHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  
- `private OnSaveHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Boolean worldMap) : System.Void`  
- `private OnSaveWorldHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `private RefreshTerrainProperties(Unity.Mathematics.float2 heightScaleOffset) : System.Void`  
- `private RemoveWorldmap() : System.Void`  
- `private ShowExportHeightmapPanel() : System.Void`  
- `private ShowExportWorldmapPanel() : System.Void`  
- `private ShowImportHeightmapPanel() : System.Void`  
- `private ShowImportWorldmapPanel() : System.Void`  

## Nested types

- `Game.UI.Editor.TerrainPanelSystem+UIPriorityComparer`  
- `Game.UI.Editor.TerrainPanelSystem+<>c`  
- `Game.UI.Editor.TerrainPanelSystem+<>c__DisplayClass9_0`  
- `Game.UI.Editor.TerrainPanelSystem+<GetHeightmaps>d__19`  

