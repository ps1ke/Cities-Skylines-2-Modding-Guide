# Game.UI.Editor.SaveAssetPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class SaveAssetPanel : Game.UI.Editor.EditorPanelBase, Game.UI.Editor.IEditorPanel
{
    private Game.UI.Editor.SaveAssetPanel+SaveCallback m_ConfirmCallback;
    private Game.UI.Editor.AssetPickerAdapter m_Adapter;
    private System.String m_FileName;

    public SaveAssetPanel(Game.UI.Localization.LocalizedString panelTitle, System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, System.Nullable<Colossal.Hash128> initialSelected, Game.UI.Editor.SaveAssetPanel+SaveCallback onConfirm, System.Action onCancel, Game.UI.Localization.LocalizedString saveButtonLabel);

    private System.String <.ctor>b__4_0();
    private System.Boolean <.ctor>b__4_1();
    private System.Void OnConfirm();
    private System.Void OnMapSelected(Game.UI.Editor.AssetItem item);
    private System.Void OnNameChange(System.String value);
}
```


## Fields

- `private Game.UI.Editor.SaveAssetPanel+SaveCallback m_ConfirmCallback`  

```csharp
private Game.UI.Editor.SaveAssetPanel+SaveCallback m_ConfirmCallback;
```

- `private Game.UI.Editor.AssetPickerAdapter m_Adapter`  

```csharp
private Game.UI.Editor.AssetPickerAdapter m_Adapter;
```

- `private System.String m_FileName`  

```csharp
private System.String m_FileName;
```


## Constructors

- `public SaveAssetPanel(Game.UI.Localization.LocalizedString panelTitle, System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, System.Nullable<Colossal.Hash128> initialSelected, Game.UI.Editor.SaveAssetPanel+SaveCallback onConfirm, System.Action onCancel, Game.UI.Localization.LocalizedString saveButtonLabel = null)`  

```csharp
public SaveAssetPanel(Game.UI.Localization.LocalizedString panelTitle, System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, System.Nullable<Colossal.Hash128> initialSelected, Game.UI.Editor.SaveAssetPanel+SaveCallback onConfirm, System.Action onCancel, Game.UI.Localization.LocalizedString saveButtonLabel);
```


## Methods

- `private <.ctor>b__4_0() : System.String`  

```csharp
private System.String <.ctor>b__4_0();
```

- `private <.ctor>b__4_1() : System.Boolean`  

```csharp
private System.Boolean <.ctor>b__4_1();
```

- `private OnConfirm() : System.Void`  

```csharp
private void OnConfirm()
	{
		m_ConfirmCallback(m_FileName, m_Adapter.selectedItem?.guid);
	}
```

- `private OnMapSelected(Game.UI.Editor.AssetItem item) : System.Void`  

```csharp
private void OnMapSelected(AssetItem item)
	{
		if (!item.fileName.Equals(m_FileName, StringComparison.OrdinalIgnoreCase))
		{
			m_FileName = item.fileName;
		}
	}
```

- `private OnNameChange(System.String value) : System.Void`  

```csharp
private void OnNameChange(string value)
	{
		m_Adapter.SelectItemByName(value, StringComparison.OrdinalIgnoreCase);
		m_FileName = value;
	}
```


## Nested types

- `Game.UI.Editor.SaveAssetPanel+SaveCallback`  

