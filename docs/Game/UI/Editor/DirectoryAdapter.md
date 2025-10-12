# Game.UI.Editor.DirectoryAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>`, `Game.UI.Editor.SearchField+IAdapter`  

## Fields

- `private Game.UI.Editor.DirectoryPanelBase m_Panel`  
- `private Game.UI.Editor.Item m_SelectedItem`  
- `private System.Collections.Generic.List<Game.UI.Editor.Item> m_Items`  
- `private System.Boolean m_Dirty`  
- `private System.Collections.Generic.HashSet<System.String> m_FavoriteIds`  
- `public System.String searchQuery`  
- `private System.String m_SearchQuery`  
- `private System.String <directoryPath>k__BackingField`  

## Properties

- `public System.String directoryPath { get; set }`  
- `public Game.UI.Editor.Item selectedItem { get; set }`  
- `public System.Collections.Generic.List<Game.UI.Editor.Item> items { get; set }`  
- `private System.Int32 Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.columnCount { private get }`  
- `private System.String Game.UI.Editor.SearchField.IAdapter.searchQuery { private get; private set }`  

## Constructors

- `public DirectoryAdapter(Game.UI.Editor.DirectoryPanelBase panel)`  

## Methods

- `private <get_items>b__16_0(Game.UI.Editor.Item item) : System.Boolean`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.Update() : System.Boolean`  

