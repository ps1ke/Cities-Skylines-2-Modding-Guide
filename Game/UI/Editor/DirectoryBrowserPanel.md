# Game.UI.Editor.DirectoryBrowserPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.DirectoryPanelBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`, `Game.UI.Editor.SearchField+IAdapter`  

## Code

```csharp
public class DirectoryBrowserPanel : Game.UI.Editor.DirectoryPanelBase, Game.UI.Editor.IEditorPanel, Game.UI.Editor.SearchField+IAdapter
{
    private readonly Game.UI.Editor.DirectoryBrowserPanel+SelectCallback m_SelectCallback;
    private readonly System.Action m_OnCloseDirectoryBrowser;
    private System.String m_SelectedDirectory;
    private System.String m_RootDirectory;
    private System.Boolean m_LimitDepthToRoot;

    public DirectoryBrowserPanel(System.String directory, System.String root, Game.UI.Editor.DirectoryBrowserPanel+SelectCallback onSelect, System.Action onCancel);

    private System.Boolean DirectoryNotSelectedOrRootSelected();
    private System.Void ImportAssets();
    private System.Boolean ImportNotReady();
    private System.Void ListDrives();
    private System.Void ListItems(System.String directory, System.Collections.Generic.List<Game.UI.Editor.Item> items);
    protected virtual System.Void OnBack();
    public virtual System.Void OnSelect(Game.UI.Editor.Item item);
    private System.Void OnSelectDirectory();
    protected virtual System.Void ShowSubDir(System.String dir);
    private System.Void TraverseToDirectory(System.String directory);
}
```


## Fields

- `private readonly Game.UI.Editor.DirectoryBrowserPanel+SelectCallback m_SelectCallback`  

```csharp
private readonly Game.UI.Editor.DirectoryBrowserPanel+SelectCallback m_SelectCallback;
```

- `private readonly System.Action m_OnCloseDirectoryBrowser`  

```csharp
private readonly System.Action m_OnCloseDirectoryBrowser;
```

- `private System.String m_SelectedDirectory`  

```csharp
private System.String m_SelectedDirectory;
```

- `private System.String m_RootDirectory`  

```csharp
private System.String m_RootDirectory;
```

- `private System.Boolean m_LimitDepthToRoot`  

```csharp
private System.Boolean m_LimitDepthToRoot;
```


## Constructors

- `public DirectoryBrowserPanel(System.String directory, System.String root, Game.UI.Editor.DirectoryBrowserPanel+SelectCallback onSelect, System.Action onCancel)`  

```csharp
public DirectoryBrowserPanel(System.String directory, System.String root, Game.UI.Editor.DirectoryBrowserPanel+SelectCallback onSelect, System.Action onCancel);
```


## Methods

- `private DirectoryNotSelectedOrRootSelected() : System.Boolean`  

```csharp
private System.Boolean DirectoryNotSelectedOrRootSelected();
```

- `private ImportAssets() : System.Void`  

```csharp
private System.Void ImportAssets();
```

- `private ImportNotReady() : System.Boolean`  

```csharp
private System.Boolean ImportNotReady();
```

- `private ListDrives() : System.Void`  

```csharp
private System.Void ListDrives();
```

- `private ListItems(System.String directory, System.Collections.Generic.List<Game.UI.Editor.Item> items) : System.Void`  

```csharp
private System.Void ListItems(System.String directory, System.Collections.Generic.List<Game.UI.Editor.Item> items);
```

- `protected virtual OnBack() : System.Void`  

```csharp
protected virtual System.Void OnBack();
```

- `public virtual OnSelect(Game.UI.Editor.Item item) : System.Void`  

```csharp
public virtual System.Void OnSelect(Game.UI.Editor.Item item);
```

- `private OnSelectDirectory() : System.Void`  

```csharp
private System.Void OnSelectDirectory();
```

- `protected virtual ShowSubDir(System.String dir) : System.Void`  

```csharp
protected virtual System.Void ShowSubDir(System.String dir);
```

- `private TraverseToDirectory(System.String directory) : System.Void`  

```csharp
private System.Void TraverseToDirectory(System.String directory);
```


## Nested types

- `Game.UI.Editor.DirectoryBrowserPanel+SelectCallback`  

