# Game.UI.Editor.SaveAssetPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Fields

- `private Game.UI.Editor.SaveAssetPanel+SaveCallback m_ConfirmCallback`  
- `private Game.UI.Editor.AssetPickerAdapter m_Adapter`  
- `private System.String m_FileName`  

## Constructors

- `public SaveAssetPanel(Game.UI.Localization.LocalizedString panelTitle, System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, System.Nullable<Colossal.Hash128> initialSelected, Game.UI.Editor.SaveAssetPanel+SaveCallback onConfirm, System.Action onCancel, Game.UI.Localization.LocalizedString saveButtonLabel = null)`  

## Methods

- `private <.ctor>b__4_0() : System.String`  
- `private <.ctor>b__4_1() : System.Boolean`  
- `private OnConfirm() : System.Void`  
- `private OnMapSelected(Game.UI.Editor.AssetItem item) : System.Void`  
- `private OnNameChange(System.String value) : System.Void`  

## Nested types

- `Game.UI.Editor.SaveAssetPanel+SaveCallback`  

