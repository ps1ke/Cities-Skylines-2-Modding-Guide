# Game.UI.Editor.LoadAssetPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class LoadAssetPanel : Game.UI.Editor.EditorPanelBase, Game.UI.Editor.IEditorPanel
{
    private Game.UI.Editor.LoadAssetPanel+LoadCallback m_ConfirmCallback;
    private Game.UI.Editor.AssetPickerAdapter m_Adapter;

    public LoadAssetPanel(Game.UI.Localization.LocalizedString panelTitle, System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, Game.UI.Editor.LoadAssetPanel+LoadCallback onConfirm, System.Action onClose);

    private System.Boolean <.ctor>b__3_0();
    private System.Void OnConfirm();
}
```


## Fields

- `private Game.UI.Editor.LoadAssetPanel+LoadCallback m_ConfirmCallback`  

```csharp
private Game.UI.Editor.LoadAssetPanel+LoadCallback m_ConfirmCallback;
```

- `private Game.UI.Editor.AssetPickerAdapter m_Adapter`  

```csharp
private Game.UI.Editor.AssetPickerAdapter m_Adapter;
```


## Constructors

- `public LoadAssetPanel(Game.UI.Localization.LocalizedString panelTitle, System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, Game.UI.Editor.LoadAssetPanel+LoadCallback onConfirm, System.Action onClose)`  

```csharp
public LoadAssetPanel(Game.UI.Localization.LocalizedString panelTitle, System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, Game.UI.Editor.LoadAssetPanel+LoadCallback onConfirm, System.Action onClose);
```


## Methods

- `private <.ctor>b__3_0() : System.Boolean`  

```csharp
private System.Boolean <.ctor>b__3_0();
```

- `private OnConfirm() : System.Void`  

```csharp
private System.Void OnConfirm();
```


## Nested types

- `Game.UI.Editor.LoadAssetPanel+LoadCallback`  

