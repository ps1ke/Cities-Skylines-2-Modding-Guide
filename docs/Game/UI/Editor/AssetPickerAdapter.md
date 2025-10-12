# Game.UI.Editor.AssetPickerAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>`, `Game.UI.Editor.SearchField+IAdapter`, `Game.UI.Editor.ItemPickerFooter+IAdapter`  

## Fields

- `private System.String m_SearchQuery`  
- `private System.Collections.Generic.List<Game.UI.Editor.AssetItem> m_Items`  
- `private System.Collections.Generic.List<Game.UI.Editor.AssetItem> m_FilteredItems`  
- `private System.Boolean m_FilteredItemsChanged`  
- `private Game.UI.Editor.AssetItem m_SelectedItem`  
- `private System.Int32 m_ColumnCount`  
- `private System.Boolean m_UseGlobalColumnCount`  
- `private System.Collections.Generic.HashSet<System.String> m_FavoriteIds`  
- `public System.Action<Game.UI.Editor.AssetItem> EventItemSelected`  

## Properties

- `public Game.UI.Editor.AssetItem selectedItem { get; set }`  
- `private Game.UI.Editor.AssetItem Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.selectedItem { private get; private set }`  
- `private System.Collections.Generic.List<Game.UI.Editor.AssetItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.items { private get }`  
- `public System.String searchQuery { get; set }`  
- `private System.Int32 Game.UI.Editor.ItemPickerFooter.IAdapter.length { private get }`  
- `public System.Int32 columnCount { get; set }`  

## Constructors

- `public AssetPickerAdapter(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, System.Int32 columnCount = 0)`  

## Methods

- `private <UpdateFilteredItems>b__16_0(Game.UI.Editor.AssetItem item) : System.Boolean`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.Update() : System.Boolean`  
- `public SelectItemByGuid(Colossal.Hash128 guid) : Game.UI.Editor.AssetItem`  
- `public SelectItemByName(System.String name, System.StringComparison comparisonType) : Game.UI.Editor.AssetItem`  
- `public SetItems(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items) : System.Void`  
- `private UpdateFilteredItems() : System.Void`  

## Nested types

- `Game.UI.Editor.AssetPickerAdapter+<>c__DisplayClass14_0`  
- `Game.UI.Editor.AssetPickerAdapter+<>c__DisplayClass15_0`  

