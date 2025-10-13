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
private DirectoryAdapter BuildAdapter(string dir)
	{
		return new DirectoryAdapter(this)
		{
			directoryPath = dir,
			items = m_Items.ToList()
		};
	}
```

- `private BuildPage(Game.UI.Editor.DirectoryAdapter adapter) : Game.UI.Widgets.IWidget`  

```csharp
private IWidget BuildPage(DirectoryAdapter adapter)
	{
		PageLayout pageLayout = new PageLayout();
		pageLayout.title = ((adapter.directoryPath != null) ? m_Directories[adapter.directoryPath].displayName : m_RootDirName);
		pageLayout.backAction = ((adapter.directoryPath != null) ? new Action(OnBack) : null);
		pageLayout.children = new IWidget[1]
		{
			new ItemPicker<Item>
			{
				adapter = adapter,
				hasFavorites = true,
				hasImages = false
			}
		};
		return pageLayout;
	}
```

- `protected virtual OnBack() : System.Void`  

```csharp
protected virtual void OnBack()
	{
		if (m_Stack.Count > 1)
		{
			m_Stack.RemoveAt(m_Stack.Count - 1);
			m_Stack.Last().selectedItem = null;
			m_Pages.RemoveAt(m_Pages.Count - 1);
			m_PageView.children = m_Pages.ToArray();
			m_PageView.currentPage = m_Stack.Count - 1;
		}
	}
```

- `public abstract OnSelect(Game.UI.Editor.Item item) : System.Void`  

```csharp
public abstract System.Void OnSelect(Game.UI.Editor.Item item);
```

- `protected virtual ShowSubDir(System.String dir) : System.Void`  

```csharp
protected virtual void ShowSubDir(string dir)
	{
		DirectoryAdapter directoryAdapter = BuildAdapter(dir);
		m_Stack.Add(directoryAdapter);
		m_Pages.Add(BuildPage(directoryAdapter));
		m_PageView.children = m_Pages.ToArray();
		m_PageView.currentPage = m_Stack.Count - 1;
	}
```


