# Game.UI.Editor.FilePickerAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem>`, `Game.UI.Editor.SearchField+IAdapter`, `Game.UI.Editor.ItemPickerFooter+IAdapter`  

## Fields

- `private System.String m_SearchQuery`  
- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_Items`  
- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_FilteredItems`  
- `private System.Boolean m_FilteredItemsChanged`  
- `private Game.UI.Editor.FileItem m_SelectedItem`  
- `private System.Int32 m_ColumnCount`  
- `public System.Action<Game.UI.Editor.FileItem> EventItemSelected`  

## Properties

- `public Game.UI.Editor.FileItem selectedItem { get; set }`  
- `private Game.UI.Editor.FileItem Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem>.IAdapter.selectedItem { private get; private set }`  
- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem>.IAdapter.items { private get }`  
- `public System.String searchQuery { get; set }`  
- `private System.Int32 Game.UI.Editor.ItemPickerFooter.IAdapter.length { private get }`  
- `public System.Int32 columnCount { get; set }`  

## Constructors

- `public FilePickerAdapter(System.Collections.Generic.IEnumerable<Game.UI.Editor.FileItem> items)`  

## Methods

- `private <UpdateFilteredItems>b__12_0(Game.UI.Editor.FileItem item) : System.Boolean`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem>.IAdapter.Update() : System.Boolean`  
- `public SelectItemByName(System.String name, System.StringComparison comparisonType) : Game.UI.Editor.FileItem`  
- `private UpdateFilteredItems() : System.Void`  

## Nested types

- `Game.UI.Editor.FilePickerAdapter+<>c__DisplayClass11_0`  

