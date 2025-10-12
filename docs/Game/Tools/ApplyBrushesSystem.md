# Game.Tools.ApplyBrushesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.ComponentTypeSet m_AppliedDeletedTypes`  
- `private Game.Tools.ApplyBrushesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ApplyBrushesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private ApplyCellMapBrush<TCell, TModifier>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, TModifier modifier, Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType, Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier> applyCellMapBrushJob) : Unity.Jobs.JobHandle`  
- `private ApplyHeight(Game.Tools.Brush brush, Unity.Entities.Entity prefab, Game.Prefabs.TerraformingType terraformingType) : System.Void`  
- `private ApplyMaterial(Game.Tools.Brush brush, Unity.Entities.Entity prefab) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.ApplyBrushesSystem+ICellModifier<TCell>`  
- `Game.Tools.ApplyBrushesSystem+NaturalResourcesModifier`  
- `Game.Tools.ApplyBrushesSystem+GroundWaterModifier`  
- `Game.Tools.ApplyBrushesSystem+ApplyCellMapBrushJob<TCell, TModifier>`  
- `Game.Tools.ApplyBrushesSystem+TypeHandle`  

