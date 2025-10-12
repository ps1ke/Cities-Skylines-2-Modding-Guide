# Game.UI.Editor.PrefabPickerPopup

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IValueFieldPopup<Game.Prefabs.PrefabBase>`  

## Fields

- `private Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> m_Accessor`  
- `private System.Type m_PrefabType`  
- `private System.Func<Game.Prefabs.PrefabBase, System.Boolean> m_Filter`  
- `private System.Boolean <nullable>k__BackingField`  
- `private Game.UI.Editor.PrefabPickerAdapter m_Adapter`  
- `private readonly System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

## Properties

- `public System.Boolean nullable { get; set }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  

## Constructors

- `public PrefabPickerPopup(System.Type prefabType, System.Func<Game.Prefabs.PrefabBase, System.Boolean> filter = null)`  

## Methods

- `public Attach(Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> accessor) : System.Void`  
- `public Detach() : System.Void`  
- `public GetDisplayValue(Game.Prefabs.PrefabBase value) : Game.UI.Localization.LocalizedString`  
- `private OnPrefabSelected(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `public Update() : System.Boolean`  

