# Game.UI.Editor.ResourcePanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup`  
- `private Game.UI.Editor.EditorSection m_TextureImportButtons`  
- `private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs`  
- `private static readonly System.String kTextureImportFolder`  

## Constructors

- `public ResourcePanelSystem()`  

## Methods

- `private ApplyFertile(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  
- `private ApplyGroundWater(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<Game.Simulation.GroundWater> data, System.Int32 x, System.Int32 y, System.Func<Game.Simulation.GroundWater, System.UInt16, Game.Simulation.GroundWater> _) : System.Void`  
- `private ApplyOil(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  
- `private ApplyOre(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  
- `private ApplyResource<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Func<TCell, System.UInt16, TCell> applyCallback) : System.Void`  
- `private ApplyTexture(UnityEngine.Texture2D texture, Game.Prefabs.TerraformingTarget target) : System.Void`  
- `private ApplyTexture<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Action<UnityEngine.Texture2D, Game.Simulation.CellMapData<TCell>, System.Int32, System.Int32, System.Func<TCell, System.UInt16, TCell>> applyCallback, System.Func<TCell, System.UInt16, TCell> resourceCallback) : System.Void`  
- `private Clear(Game.Prefabs.TerraformingTarget target) : System.Void`  
- `private ClearFertile(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  
- `private ClearGroundWater(Game.Simulation.GroundWater _) : Game.Simulation.GroundWater`  
- `private ClearMap<TCell>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Func<TCell, TCell> clearCallback) : System.Void`  
- `private ClearOil(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  
- `private ClearOre(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  
- `private static GetTextures() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  
- `private ImportTexture(Game.Prefabs.TerraformingTarget target) : System.Void`  
- `private static IsResourceTerraformingPrefab(Game.Prefabs.TerraformingPrefab prefab) : System.Boolean`  
- `protected virtual OnCancel() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnLoadTexture(Colossal.Hash128 guid, Game.Prefabs.TerraformingTarget target) : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `private Sample<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Int32 max) : System.Int32`  

## Nested types

- `Game.UI.Editor.ResourcePanelSystem+<>c`  
- `Game.UI.Editor.ResourcePanelSystem+<>c__DisplayClass10_0`  
- `Game.UI.Editor.ResourcePanelSystem+<>c__DisplayClass14_0`  
- `Game.UI.Editor.ResourcePanelSystem+<GetTextures>d__15`  

