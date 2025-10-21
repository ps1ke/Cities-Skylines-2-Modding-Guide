# Game.UI.Editor.TerrainPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class TerrainPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup;
    private Game.UI.Widgets.IconButtonGroup m_MaterialButtonGroup;
    private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs;
    private static readonly System.String kHeightmapFolder;

    public TerrainPanelSystem();

    private System.Double <OnCreate>b__8_0();
    private System.Void <OnCreate>b__8_1(System.Double val);
    private System.Boolean <OnCreate>b__8_2();
    private System.Boolean <OnCreate>b__8_3();
    private System.Void DisplayHeightmapError();
    private static System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetHeightmaps();
    protected virtual System.Boolean OnCancel();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnLoadHeightmap(Colossal.Hash128 guid);
    private System.Void OnLoadWorldHeightmap(Colossal.Hash128 guid);
    private System.Void OnSaveHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid);
    private System.Void OnSaveHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Boolean worldMap);
    private System.Void OnSaveWorldHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    private System.Void RefreshTerrainProperties(Unity.Mathematics.float2 heightScaleOffset);
    private System.Void RemoveWorldmap();
    private System.Void ShowExportHeightmapPanel();
    private System.Void ShowExportWorldmapPanel();
    private System.Void ShowImportHeightmapPanel();
    private System.Void ShowImportWorldmapPanel();
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

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup`  

```csharp
private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup;
```

- `private Game.UI.Widgets.IconButtonGroup m_MaterialButtonGroup`  

```csharp
private Game.UI.Widgets.IconButtonGroup m_MaterialButtonGroup;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs;
```

- `private static readonly System.String kHeightmapFolder`  

```csharp
private static readonly System.String kHeightmapFolder;
```


## Constructors

- `public TerrainPanelSystem()`  

```csharp
public TerrainPanelSystem();
```


## Methods

- `private <OnCreate>b__8_0() : System.Double`  

```csharp
private System.Double <OnCreate>b__8_0();
```

- `private <OnCreate>b__8_1(System.Double val) : System.Void`  

```csharp
private System.Void <OnCreate>b__8_1(System.Double val);
```

- `private <OnCreate>b__8_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__8_2();
```

- `private <OnCreate>b__8_3() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__8_3();
```

- `private DisplayHeightmapError() : System.Void`  

```csharp
private System.Void DisplayHeightmapError();
```

- `private static GetHeightmaps() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private static System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetHeightmaps();
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

- `private OnLoadHeightmap(Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void OnLoadHeightmap(Colossal.Hash128 guid);
```

- `private OnLoadWorldHeightmap(Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void OnLoadWorldHeightmap(Colossal.Hash128 guid);
```

- `private OnSaveHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
private System.Void OnSaveHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid);
```

- `private OnSaveHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Boolean worldMap) : System.Void`  

```csharp
private System.Void OnSaveHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Boolean worldMap);
```

- `private OnSaveWorldHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
private System.Void OnSaveWorldHeightmap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `private RefreshTerrainProperties(Unity.Mathematics.float2 heightScaleOffset) : System.Void`  

```csharp
private System.Void RefreshTerrainProperties(Unity.Mathematics.float2 heightScaleOffset);
```

- `private RemoveWorldmap() : System.Void`  

```csharp
private System.Void RemoveWorldmap();
```

- `private ShowExportHeightmapPanel() : System.Void`  

```csharp
private System.Void ShowExportHeightmapPanel();
```

- `private ShowExportWorldmapPanel() : System.Void`  

```csharp
private System.Void ShowExportWorldmapPanel();
```

- `private ShowImportHeightmapPanel() : System.Void`  

```csharp
private System.Void ShowImportHeightmapPanel();
```

- `private ShowImportWorldmapPanel() : System.Void`  

```csharp
private System.Void ShowImportWorldmapPanel();
```


## Nested types

- `Game.UI.Editor.TerrainPanelSystem+UIPriorityComparer`  
- `Game.UI.Editor.TerrainPanelSystem+<>c`  
- `Game.UI.Editor.TerrainPanelSystem+<>c__DisplayClass9_0`  
- `Game.UI.Editor.TerrainPanelSystem+<GetHeightmaps>d__19`  

