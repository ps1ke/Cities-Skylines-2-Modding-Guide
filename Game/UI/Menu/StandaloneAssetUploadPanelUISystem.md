# Game.UI.Menu.StandaloneAssetUploadPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class StandaloneAssetUploadPanelUISystem : Game.UI.UISystemBase
{
    private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelUISystem;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Visible;
    private static readonly System.String kGroup;

    public StandaloneAssetUploadPanelUISystem();

    private System.Void OnChildrenChange(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children);
    private System.Void OnClose();
    protected virtual System.Void OnCreate();
    public System.Void Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy);
}
```


## Fields

- `private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelUISystem`  

```csharp
private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelUISystem;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Visible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Visible;
```

- `private static readonly System.String kGroup`  

```csharp
private static readonly System.String kGroup;
```


## Constructors

- `public StandaloneAssetUploadPanelUISystem()`  

```csharp
public StandaloneAssetUploadPanelUISystem();
```


## Methods

- `private OnChildrenChange(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children) : System.Void`  

```csharp
private System.Void OnChildrenChange(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children);
```

- `private OnClose() : System.Void`  

```csharp
private System.Void OnClose();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `public Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy = True) : System.Void`  

```csharp
public System.Void Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy);
```


