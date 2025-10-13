# Game.UI.Editor.DirectoryPanelBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `Game.UI.Editor.EditorPanelBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`, `Game.UI.Editor.SearchField+IAdapter`  

## Code

```csharp
public abstract class DirectoryPanelBase : Game.UI.Editor.EditorPanelBase, Game.UI.Editor.IEditorPanel, Game.UI.Editor.SearchField+IAdapter
{
    protected System.Collections.Generic.List<Game.UI.Editor.Item> m_Items;
    protected System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.Item> m_Directories;
    protected Game.UI.Localization.LocalizedString m_RootDirName;
    protected Game.UI.Widgets.PageView m_PageView;
    protected readonly System.Collections.Generic.List<Game.UI.Editor.DirectoryAdapter> m_Stack;
    protected readonly System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Pages;
    protected static Colossal.Logging.ILog log;
    protected static const System.Char kDirSeparator;

    private System.String Game.UI.Editor.SearchField.IAdapter.searchQuery { private get; private set; }

    protected DirectoryPanelBase();

    private Game.UI.Editor.DirectoryAdapter BuildAdapter(System.String dir);
    private Game.UI.Widgets.IWidget BuildPage(Game.UI.Editor.DirectoryAdapter adapter);
    protected virtual System.Void OnBack();
    public abstract System.Void OnSelect(Game.UI.Editor.Item item);
    protected virtual System.Void ShowSubDir(System.String dir);
}
```


## Fields

- `protected System.Collections.Generic.List<Game.UI.Editor.Item> m_Items`  

```csharp
protected System.Collections.Generic.List<Game.UI.Editor.Item> m_Items;
```

- `protected System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.Item> m_Directories`  

```csharp
protected System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.Item> m_Directories;
```

- `protected Game.UI.Localization.LocalizedString m_RootDirName`  

```csharp
protected Game.UI.Localization.LocalizedString m_RootDirName;
```

- `protected Game.UI.Widgets.PageView m_PageView`  

```csharp
protected Game.UI.Widgets.PageView m_PageView;
```

- `protected readonly System.Collections.Generic.List<Game.UI.Editor.DirectoryAdapter> m_Stack`  

```csharp
protected readonly System.Collections.Generic.List<Game.UI.Editor.DirectoryAdapter> m_Stack;
```

- `protected readonly System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Pages`  

```csharp
protected readonly System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Pages;
```

- `protected static Colossal.Logging.ILog log`  

```csharp
protected static Colossal.Logging.ILog log;
```

- `protected static const System.Char kDirSeparator`  

```csharp
protected static const System.Char kDirSeparator;
```


## Properties

- `private System.String Game.UI.Editor.SearchField.IAdapter.searchQuery { private get; private set }`  

```csharp
private System.String Game.UI.Editor.SearchField.IAdapter.searchQuery { private get; private set; }
```


## Constructors

- `protected DirectoryPanelBase()`  

```csharp
protected DirectoryPanelBase();
```


## Methods

- `private BuildAdapter(System.String dir) : Game.UI.Editor.DirectoryAdapter`  

```csharp
private Game.UI.Editor.DirectoryAdapter BuildAdapter(System.String dir);
```

- `private BuildPage(Game.UI.Editor.DirectoryAdapter adapter) : Game.UI.Widgets.IWidget`  

```csharp
private Game.UI.Widgets.IWidget BuildPage(Game.UI.Editor.DirectoryAdapter adapter);
```

- `protected virtual OnBack() : System.Void`  

```csharp
protected virtual System.Void OnBack();
```

- `public abstract OnSelect(Game.UI.Editor.Item item) : System.Void`  

```csharp
public abstract System.Void OnSelect(Game.UI.Editor.Item item);
```

- `protected virtual ShowSubDir(System.String dir) : System.Void`  

```csharp
protected virtual System.Void ShowSubDir(System.String dir);
```


