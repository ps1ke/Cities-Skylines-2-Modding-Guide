# Game.UI.Editor.AssetImportPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Fields

- `private System.String m_SelectedProjectRoot`  
- `private System.String m_SelectedDirectory`  
- `private System.Boolean m_ProjectRootSelected`  
- `private Game.UI.Widgets.DirectoryPickerButton m_OpenProjectRootButton`  
- `private Game.UI.Widgets.DirectoryPickerButton m_OpenSelectedAssetPathButton`  
- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_Assets`  
- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_CachedAssets`  
- `private Game.UI.Editor.FilePickerAdapter m_Adapter`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem> m_AssetList`  
- `private Game.UI.Editor.ItemPickerFooter m_ItemPickerFooter`  
- `private Game.Prefabs.PrefabBase m_SelectedTemplate`  
- `private Game.UI.Widgets.Button m_ImportButton`  
- `private System.Boolean m_Importing`  

## Properties

- `private System.Boolean importing { private get; private set }`  

## Constructors

- `public AssetImportPanel()`  

## Methods

- `private <OnStartRunning>b__16_0() : Game.Prefabs.PrefabBase`  
- `private <OnStartRunning>b__16_1(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `private CloseDirectoryBrowser() : System.Void`  
- `private GetAssets() : System.Collections.Generic.IEnumerable<Game.UI.Editor.FileItem>`  
- `private ImportAssets() : System.Void`  
- `public static ImportAssets(System.String selectedProjectRoot, System.String selectedDirectory, Game.Prefabs.PrefabBase selectedTemplate, Unity.Entities.World world, Colossal.Logging.ILog log) : System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory>`  
- `private IsImportDisabled() : System.Boolean`  
- `private IsSelectedAssetFolderDisabled() : System.Boolean`  
- `private OnAssetSelected(Game.UI.Editor.FileItem item) : System.Void`  
- `private OnLoadAsset(System.Guid guid) : System.Void`  
- `private OnSelectDirectory(System.String directory) : System.Void`  
- `private OnSelectProjectRoot(System.String directory) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `private OpenAssetSubDirectory() : System.Void`  
- `private OpenDirectory() : System.Void`  
- `private static ReportProgress(System.String title, System.String info, System.Single progress) : System.Boolean`  

## Nested types

- `Game.UI.Editor.AssetImportPanel+PrefabFactory`  
- `Game.UI.Editor.AssetImportPanel+<GetAssets>d__24`  
- `Game.UI.Editor.AssetImportPanel+<ImportAssets>d__29`  
- `Game.UI.Editor.AssetImportPanel+<ImportAssets>d__30`  

