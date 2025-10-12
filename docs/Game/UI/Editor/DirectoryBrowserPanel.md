# Game.UI.Editor.DirectoryBrowserPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.DirectoryPanelBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`, `Game.UI.Editor.SearchField+IAdapter`  

## Fields

- `private readonly Game.UI.Editor.DirectoryBrowserPanel+SelectCallback m_SelectCallback`  
- `private readonly System.Action m_OnCloseDirectoryBrowser`  
- `private System.String m_SelectedDirectory`  
- `private System.String m_RootDirectory`  
- `private System.Boolean m_LimitDepthToRoot`  

## Constructors

- `public DirectoryBrowserPanel(System.String directory, System.String root, Game.UI.Editor.DirectoryBrowserPanel+SelectCallback onSelect, System.Action onCancel)`  

## Methods

- `private DirectoryNotSelectedOrRootSelected() : System.Boolean`  
- `private ImportAssets() : System.Void`  
- `private ImportNotReady() : System.Boolean`  
- `private ListDrives() : System.Void`  
- `private ListItems(System.String directory, System.Collections.Generic.List<Game.UI.Editor.Item> items) : System.Void`  
- `protected virtual OnBack() : System.Void`  
- `public virtual OnSelect(Game.UI.Editor.Item item) : System.Void`  
- `private OnSelectDirectory() : System.Void`  
- `protected virtual ShowSubDir(System.String dir) : System.Void`  
- `private TraverseToDirectory(System.String directory) : System.Void`  

## Nested types

- `Game.UI.Editor.DirectoryBrowserPanel+SelectCallback`  

