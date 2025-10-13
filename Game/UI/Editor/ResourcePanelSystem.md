# Game.UI.Editor.ResourcePanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class ResourcePanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup;
    private Game.UI.Editor.EditorSection m_TextureImportButtons;
    private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs;
    private static readonly System.String kTextureImportFolder;

    public ResourcePanelSystem();

    private Game.Simulation.NaturalResourceCell ApplyFertile(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
    private System.Void ApplyGroundWater(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<Game.Simulation.GroundWater> data, System.Int32 x, System.Int32 y, System.Func<Game.Simulation.GroundWater, System.UInt16, Game.Simulation.GroundWater> _);
    private Game.Simulation.NaturalResourceCell ApplyOil(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
    private Game.Simulation.NaturalResourceCell ApplyOre(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
    private System.Void ApplyResource<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Func<TCell, System.UInt16, TCell> applyCallback);
    private System.Void ApplyTexture(UnityEngine.Texture2D texture, Game.Prefabs.TerraformingTarget target);
    private System.Void ApplyTexture<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Action<UnityEngine.Texture2D, Game.Simulation.CellMapData<TCell>, System.Int32, System.Int32, System.Func<TCell, System.UInt16, TCell>> applyCallback, System.Func<TCell, System.UInt16, TCell> resourceCallback);
    private System.Void Clear(Game.Prefabs.TerraformingTarget target);
    private Game.Simulation.NaturalResourceCell ClearFertile(Game.Simulation.NaturalResourceCell cell);
    private Game.Simulation.GroundWater ClearGroundWater(Game.Simulation.GroundWater _);
    private System.Void ClearMap<TCell>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Func<TCell, TCell> clearCallback);
    private Game.Simulation.NaturalResourceCell ClearOil(Game.Simulation.NaturalResourceCell cell);
    private Game.Simulation.NaturalResourceCell ClearOre(Game.Simulation.NaturalResourceCell cell);
    private static System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetTextures();
    private System.Void ImportTexture(Game.Prefabs.TerraformingTarget target);
    private static System.Boolean IsResourceTerraformingPrefab(Game.Prefabs.TerraformingPrefab prefab);
    protected virtual System.Boolean OnCancel();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnLoadTexture(Colossal.Hash128 guid, Game.Prefabs.TerraformingTarget target);
    protected virtual System.Void OnStopRunning();
    private System.Int32 Sample<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Int32 max);
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

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup`  

```csharp
private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup;
```

- `private Game.UI.Editor.EditorSection m_TextureImportButtons`  

```csharp
private Game.UI.Editor.EditorSection m_TextureImportButtons;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs;
```

- `private static readonly System.String kTextureImportFolder`  

```csharp
private static readonly System.String kTextureImportFolder;
```


## Constructors

- `public ResourcePanelSystem()`  

```csharp
public ResourcePanelSystem();
```


## Methods

- `private ApplyFertile(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  

```csharp
private Game.Simulation.NaturalResourceCell ApplyFertile(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
```

- `private ApplyGroundWater(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<Game.Simulation.GroundWater> data, System.Int32 x, System.Int32 y, System.Func<Game.Simulation.GroundWater, System.UInt16, Game.Simulation.GroundWater> _) : System.Void`  

```csharp
private System.Void ApplyGroundWater(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<Game.Simulation.GroundWater> data, System.Int32 x, System.Int32 y, System.Func<Game.Simulation.GroundWater, System.UInt16, Game.Simulation.GroundWater> _);
```

- `private ApplyOil(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  

```csharp
private Game.Simulation.NaturalResourceCell ApplyOil(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
```

- `private ApplyOre(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  

```csharp
private Game.Simulation.NaturalResourceCell ApplyOre(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
```

- `private ApplyResource<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Func<TCell, System.UInt16, TCell> applyCallback) : System.Void`  

```csharp
private System.Void ApplyResource<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Func<TCell, System.UInt16, TCell> applyCallback);
```

- `private ApplyTexture(UnityEngine.Texture2D texture, Game.Prefabs.TerraformingTarget target) : System.Void`  

```csharp
private System.Void ApplyTexture(UnityEngine.Texture2D texture, Game.Prefabs.TerraformingTarget target);
```

- `private ApplyTexture<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Action<UnityEngine.Texture2D, Game.Simulation.CellMapData<TCell>, System.Int32, System.Int32, System.Func<TCell, System.UInt16, TCell>> applyCallback, System.Func<TCell, System.UInt16, TCell> resourceCallback) : System.Void`  

```csharp
private System.Void ApplyTexture<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Action<UnityEngine.Texture2D, Game.Simulation.CellMapData<TCell>, System.Int32, System.Int32, System.Func<TCell, System.UInt16, TCell>> applyCallback, System.Func<TCell, System.UInt16, TCell> resourceCallback);
```

- `private Clear(Game.Prefabs.TerraformingTarget target) : System.Void`  

```csharp
private System.Void Clear(Game.Prefabs.TerraformingTarget target);
```

- `private ClearFertile(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  

```csharp
private Game.Simulation.NaturalResourceCell ClearFertile(Game.Simulation.NaturalResourceCell cell);
```

- `private ClearGroundWater(Game.Simulation.GroundWater _) : Game.Simulation.GroundWater`  

```csharp
private Game.Simulation.GroundWater ClearGroundWater(Game.Simulation.GroundWater _);
```

- `private ClearMap<TCell>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Func<TCell, TCell> clearCallback) : System.Void`  

```csharp
private System.Void ClearMap<TCell>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Func<TCell, TCell> clearCallback);
```

- `private ClearOil(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  

```csharp
private Game.Simulation.NaturalResourceCell ClearOil(Game.Simulation.NaturalResourceCell cell);
```

- `private ClearOre(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  

```csharp
private Game.Simulation.NaturalResourceCell ClearOre(Game.Simulation.NaturalResourceCell cell);
```

- `private static GetTextures() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private static System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetTextures();
```

- `private ImportTexture(Game.Prefabs.TerraformingTarget target) : System.Void`  

```csharp
private System.Void ImportTexture(Game.Prefabs.TerraformingTarget target);
```

- `private static IsResourceTerraformingPrefab(Game.Prefabs.TerraformingPrefab prefab) : System.Boolean`  

```csharp
private static System.Boolean IsResourceTerraformingPrefab(Game.Prefabs.TerraformingPrefab prefab);
```

- `protected virtual OnCancel() : System.Boolean`  

```csharp
protected virtual System.Boolean OnCancel();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnLoadTexture(Colossal.Hash128 guid, Game.Prefabs.TerraformingTarget target) : System.Void`  

```csharp
private System.Void OnLoadTexture(Colossal.Hash128 guid, Game.Prefabs.TerraformingTarget target);
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `private Sample<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Int32 max) : System.Int32`  

```csharp
private System.Int32 Sample<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Int32 max);
```


## Nested types

- `Game.UI.Editor.ResourcePanelSystem+<>c`  
- `Game.UI.Editor.ResourcePanelSystem+<>c__DisplayClass10_0`  
- `Game.UI.Editor.ResourcePanelSystem+<>c__DisplayClass14_0`  
- `Game.UI.Editor.ResourcePanelSystem+<GetTextures>d__15`  

