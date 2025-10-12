# Game.UI.Editor.DirectoryPanelBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `Game.UI.Editor.EditorPanelBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`, `Game.UI.Editor.SearchField+IAdapter`  

## Fields

- `protected System.Collections.Generic.List<Game.UI.Editor.Item> m_Items`  
- `protected System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.Item> m_Directories`  
- `protected Game.UI.Localization.LocalizedString m_RootDirName`  
- `protected Game.UI.Widgets.PageView m_PageView`  
- `protected readonly System.Collections.Generic.List<Game.UI.Editor.DirectoryAdapter> m_Stack`  
- `protected readonly System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Pages`  
- `protected static Colossal.Logging.ILog log`  
- `protected static const System.Char kDirSeparator`  

## Properties

- `private System.String Game.UI.Editor.SearchField.IAdapter.searchQuery { private get; private set }`  

## Constructors

- `protected DirectoryPanelBase()`  

## Methods

- `private BuildAdapter(System.String dir) : Game.UI.Editor.DirectoryAdapter`  
- `private BuildPage(Game.UI.Editor.DirectoryAdapter adapter) : Game.UI.Widgets.IWidget`  
- `protected virtual OnBack() : System.Void`  
- `public abstract OnSelect(Game.UI.Editor.Item item) : System.Void`  
- `protected virtual ShowSubDir(System.String dir) : System.Void`  

