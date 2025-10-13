# Game.UI.Editor.EditorAssetUploadPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class EditorAssetUploadPanel : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelSystem;

    public EditorAssetUploadPanel();

    private System.Void OnChildrenChange(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> _children);
    protected virtual System.Boolean OnClose();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    public System.Void Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy);
}
```


## Fields

- `private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelSystem`  

```csharp
private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelSystem;
```


## Constructors

- `public EditorAssetUploadPanel()`  

```csharp
public EditorAssetUploadPanel();
```


## Methods

- `private OnChildrenChange(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> _children) : System.Void`  

```csharp
private System.Void OnChildrenChange(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> _children);
```

- `protected virtual OnClose() : System.Boolean`  

```csharp
protected virtual System.Boolean OnClose();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `public Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy = True) : System.Void`  

```csharp
public System.Void Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy);
```


