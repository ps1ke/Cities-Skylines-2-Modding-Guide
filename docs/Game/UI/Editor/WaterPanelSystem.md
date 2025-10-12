# Game.UI.Editor.WaterPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.WaterToolSystem m_WaterToolSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedSourceQuery`  
- `private Unity.Entities.EntityArchetype m_WaterSourceArchetype`  
- `private Game.UI.Editor.WaterPanelSystem+WaterConfig m_Config`  
- `private static readonly System.Int32[] kWaterSpeedValues`  

## Constructors

- `public WaterPanelSystem()`  

## Methods

- `private AddBorderSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+BorderWaterSource source, System.Int32 constantDepth, Game.Simulation.TerrainHeightData& terrainHeightData) : System.Void`  
- `private AddSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+WaterSource source, System.Int32 constantDepth, System.Single& amount, Game.Simulation.TerrainHeightData& terrainHeightData) : System.Void`  
- `private ApplyWaterSources() : System.Void`  
- `private BuildWaterSpeedToggles() : Game.UI.Widgets.IWidget[]`  
- `public FetchWaterSources() : System.Void`  
- `private GetSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> sources, System.Int32& sourceCount) : Unity.Entities.Entity`  
- `protected virtual OnCancel() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

## Nested types

- `Game.UI.Editor.WaterPanelSystem+WaterConfig`  
- `Game.UI.Editor.WaterPanelSystem+<>c__DisplayClass11_0`  

