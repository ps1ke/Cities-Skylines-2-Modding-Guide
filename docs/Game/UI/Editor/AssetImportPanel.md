# Game.UI.Editor.AssetImportPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class AssetImportPanel : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private System.String m_SelectedProjectRoot;
    private System.String m_SelectedDirectory;
    private System.Boolean m_ProjectRootSelected;
    private Game.UI.Widgets.DirectoryPickerButton m_OpenProjectRootButton;
    private Game.UI.Widgets.DirectoryPickerButton m_OpenSelectedAssetPathButton;
    private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_Assets;
    private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_CachedAssets;
    private Game.UI.Editor.FilePickerAdapter m_Adapter;
    private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem> m_AssetList;
    private Game.UI.Editor.ItemPickerFooter m_ItemPickerFooter;
    private Game.Prefabs.PrefabBase m_SelectedTemplate;
    private Game.UI.Widgets.Button m_ImportButton;
    private System.Boolean m_Importing;

    private System.Boolean importing { private get; private set; }

    public AssetImportPanel();

    private Game.Prefabs.PrefabBase <OnStartRunning>b__16_0();
    private System.Void <OnStartRunning>b__16_1(Game.Prefabs.PrefabBase prefab);
    private System.Void CloseDirectoryBrowser();
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.FileItem> GetAssets();
    private System.Void ImportAssets();
    public static System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory> ImportAssets(System.String selectedProjectRoot, System.String selectedDirectory, Game.Prefabs.PrefabBase selectedTemplate, Unity.Entities.World world, Colossal.Logging.ILog log);
    private System.Boolean IsImportDisabled();
    private System.Boolean IsSelectedAssetFolderDisabled();
    private System.Void OnAssetSelected(Game.UI.Editor.FileItem item);
    private System.Void OnLoadAsset(System.Guid guid);
    private System.Void OnSelectDirectory(System.String directory);
    private System.Void OnSelectProjectRoot(System.String directory);
    protected virtual System.Void OnStartRunning();
    private System.Void OpenAssetSubDirectory();
    private System.Void OpenDirectory();
    private static System.Boolean ReportProgress(System.String title, System.String info, System.Single progress);
}
```


## Fields

- `private System.String m_SelectedProjectRoot`  

```csharp
private System.String m_SelectedProjectRoot;
```

- `private System.String m_SelectedDirectory`  

```csharp
private System.String m_SelectedDirectory;
```

- `private System.Boolean m_ProjectRootSelected`  

```csharp
private System.Boolean m_ProjectRootSelected;
```

- `private Game.UI.Widgets.DirectoryPickerButton m_OpenProjectRootButton`  

```csharp
private Game.UI.Widgets.DirectoryPickerButton m_OpenProjectRootButton;
```

- `private Game.UI.Widgets.DirectoryPickerButton m_OpenSelectedAssetPathButton`  

```csharp
private Game.UI.Widgets.DirectoryPickerButton m_OpenSelectedAssetPathButton;
```

- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_Assets`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_Assets;
```

- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_CachedAssets`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_CachedAssets;
```

- `private Game.UI.Editor.FilePickerAdapter m_Adapter`  

```csharp
private Game.UI.Editor.FilePickerAdapter m_Adapter;
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem> m_AssetList`  

```csharp
private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem> m_AssetList;
```

- `private Game.UI.Editor.ItemPickerFooter m_ItemPickerFooter`  

```csharp
private Game.UI.Editor.ItemPickerFooter m_ItemPickerFooter;
```

- `private Game.Prefabs.PrefabBase m_SelectedTemplate`  

```csharp
private Game.Prefabs.PrefabBase m_SelectedTemplate;
```

- `private Game.UI.Widgets.Button m_ImportButton`  

```csharp
private Game.UI.Widgets.Button m_ImportButton;
```

- `private System.Boolean m_Importing`  

```csharp
private System.Boolean m_Importing;
```


## Properties

- `private System.Boolean importing { private get; private set }`  

```csharp
private System.Boolean importing { private get; private set; }
```


## Constructors

- `public AssetImportPanel()`  

```csharp
public AssetImportPanel();
```


## Methods

- `private <OnStartRunning>b__16_0() : Game.Prefabs.PrefabBase`  

```csharp
private Game.Prefabs.PrefabBase <OnStartRunning>b__16_0();
```

- `private <OnStartRunning>b__16_1(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void <OnStartRunning>b__16_1(Game.Prefabs.PrefabBase prefab);
```

- `private CloseDirectoryBrowser() : System.Void`  

```csharp
private System.Void CloseDirectoryBrowser();
```

- `private GetAssets() : System.Collections.Generic.IEnumerable<Game.UI.Editor.FileItem>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.FileItem> GetAssets();
```

- `private ImportAssets() : System.Void`  

```csharp
private System.Void ImportAssets();
```

- `public static ImportAssets(System.String selectedProjectRoot, System.String selectedDirectory, Game.Prefabs.PrefabBase selectedTemplate, Unity.Entities.World world, Colossal.Logging.ILog log) : System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory>`  

```csharp
public static System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory> ImportAssets(System.String selectedProjectRoot, System.String selectedDirectory, Game.Prefabs.PrefabBase selectedTemplate, Unity.Entities.World world, Colossal.Logging.ILog log);
```

- `private IsImportDisabled() : System.Boolean`  

```csharp
private System.Boolean IsImportDisabled();
```

- `private IsSelectedAssetFolderDisabled() : System.Boolean`  

```csharp
private System.Boolean IsSelectedAssetFolderDisabled();
```

- `private OnAssetSelected(Game.UI.Editor.FileItem item) : System.Void`  

```csharp
private System.Void OnAssetSelected(Game.UI.Editor.FileItem item);
```

- `private OnLoadAsset(System.Guid guid) : System.Void`  

```csharp
private System.Void OnLoadAsset(System.Guid guid);
```

- `private OnSelectDirectory(System.String directory) : System.Void`  

```csharp
private System.Void OnSelectDirectory(System.String directory);
```

- `private OnSelectProjectRoot(System.String directory) : System.Void`  

```csharp
private System.Void OnSelectProjectRoot(System.String directory);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `private OpenAssetSubDirectory() : System.Void`  

```csharp
private System.Void OpenAssetSubDirectory();
```

- `private OpenDirectory() : System.Void`  

```csharp
private System.Void OpenDirectory();
```

- `private static ReportProgress(System.String title, System.String info, System.Single progress) : System.Boolean`  

```csharp
private static System.Boolean ReportProgress(System.String title, System.String info, System.Single progress);
```


## Nested types

- `Game.UI.Editor.AssetImportPanel+PrefabFactory`  
- `Game.UI.Editor.AssetImportPanel+<GetAssets>d__24`  
- `Game.UI.Editor.AssetImportPanel+<ImportAssets>d__29`  
- `Game.UI.Editor.AssetImportPanel+<ImportAssets>d__30`  

