# Game.UI.Editor.ClimatePanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`, `Game.UI.Editor.SeasonsField+IAdapter`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  
- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  
- `private Unity.Entities.EntityQuery m_ClimateQuery`  
- `private Unity.Entities.EntityQuery m_ClimateSeasonQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Game.UI.Editor.SeasonsField+SeasonCurves m_SeasonsCurves`  
- `private Unity.Entities.EntityQuery m_RenderQuery`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Prefabs.InfoviewPrefab m_WindInfoview`  
- `private System.Double m_LastWindDirection`  
- `private System.Int32 m_LastClimateHash`  
- `private System.Int32 m_InfoviewCooldown`  
- `private Game.UI.Editor.EditorSection m_InspectorSection`  
- `private Game.UI.Widgets.EditorGenerator m_Generator`  
- `private UnityEngine.Coroutine m_DelayedInfomodeReset`  
- `private Game.Prefabs.InfoviewPrefab m_PreviousInfoview`  
- `private Unity.Entities.EntityQuery m_AllInfoviewQuery`  
- `private Unity.Entities.Entity <selectedSeason>k__BackingField`  
- `private Game.UI.Editor.ClimatePanelSystem+TypeHandle __TypeHandle`  

## Properties

- `private Game.Prefabs.Climate.ClimatePrefab currentClimate { private get; private set }`  
- `private System.Double windDirection { private get; private set }`  
- `private System.Collections.Generic.IEnumerable<Game.Simulation.ClimateSystem+SeasonInfo> Game.UI.Editor.SeasonsField.IAdapter.seasons { private get; private set }`  
- `private Game.UI.Editor.SeasonsField+SeasonCurves Game.UI.Editor.SeasonsField.IAdapter.curves { private get; private set }`  
- `public Unity.Entities.Entity selectedSeason { get; set }`  

## Constructors

- `public ClimatePanelSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private <RebuildInspector>b__28_0() : Game.Prefabs.PrefabBase`  
- `private <RebuildInspector>b__28_1(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `private DisableInfomode() : System.Collections.IEnumerator`  
- `private Duplicate() : System.Void`  
- `private GetWindInfoView() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  
- `public RebuildCurves() : System.Void`  
- `private RebuildInspector() : System.Void`  

## Nested types

- `Game.UI.Editor.ClimatePanelSystem+TypeHandle`  
- `Game.UI.Editor.ClimatePanelSystem+<DisableInfomode>d__30`  

