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
public LoadAssetPanel(LocalizedString panelTitle, IEnumerable<AssetItem> items, LoadCallback onConfirm, Action onClose)
	{
		m_ConfirmCallback = onConfirm;
		m_Adapter = new AssetPickerAdapter(items);
		base.title = panelTitle;
		base.children = new IWidget[4]
		{
			new SearchField
			{
				adapter = m_Adapter
			},
			new ItemPicker<AssetItem>
			{
				adapter = m_Adapter,
				hasFavorites = true
			},
			new ItemPickerFooter
			{
				adapter = m_Adapter
			},
			ButtonRow.WithChildren(new Button[2]
			{
				new Button
				{
					displayName = "Editor.LOAD",
					disabled = () => m_Adapter.selectedItem == null,
					action = OnConfirm
				},
				new Button
				{
					displayName = "Common.CANCEL",
					action = onClose
				}
			})
		};
	}
```


## Methods

- `private <.ctor>b__3_0() : System.Boolean`  

```csharp
private System.Boolean <.ctor>b__3_0();
```

- `private OnConfirm() : System.Void`  

```csharp
private void OnConfirm()
	{
		m_ConfirmCallback(m_Adapter.selectedItem.guid);
	}
```


## Nested types

- `Game.UI.Editor.LoadAssetPanel+LoadCallback`  

