# Game.UI.Editor.PrefabPickerAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>`, `Game.UI.Editor.PopupSearchField+IAdapter`, `Game.UI.Editor.SearchField+IAdapter`, `Game.UI.Editor.ItemPickerFooter+IAdapter`, `Game.UI.Editor.FilterMenu+IAdapter`  

## Fields

- `private System.Boolean <displayPrefabTypeTooltip>k__BackingField`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private System.String m_SearchQuery`  
- `private System.Boolean m_SearchQueryIsFavorite`  
- `private System.Boolean m_SearchQueryChanged`  
- `private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> m_Items`  
- `private System.Boolean m_ItemsChanged`  
- `private System.Collections.Generic.List<System.String> m_AvailableFilters`  
- `private System.Collections.Generic.List<System.String> m_ActiveFilters`  
- `private System.Boolean m_ActiveFiltersChanged`  
- `private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> m_FilteredItems`  
- `private System.Boolean m_FilteredItemsChanged`  
- `private Game.UI.Editor.PrefabItem m_SelectedItem`  
- `private Game.Prefabs.PrefabBase m_SelectedPrefab`  
- `private System.Collections.Generic.List<System.String> m_SearchHistory`  
- `private System.Collections.Generic.HashSet<System.String> m_SearchFavorites`  
- `private System.Collections.Generic.List<Game.UI.Editor.PopupSearchField+Suggestion> m_SearchSuggestions`  
- `private System.Collections.Generic.HashSet<System.String> m_FavoriteIds`  
- `private System.Int32 m_ColumnCount`  
- `private System.Action <onAvailableFiltersChanged>k__BackingField`  
- `public System.Action<Game.Prefabs.PrefabBase> EventPrefabSelected`  
- `public static const System.Int32 kMaxHistoryLength`  
- `public static const System.Int32 kMaxHistoryDisplayLength`  

## Properties

- `public System.Boolean displayPrefabTypeTooltip { get; set }`  
- `public Game.Prefabs.PrefabBase selectedPrefab { get; set }`  
- `public System.Collections.Generic.List<System.String> availableFilters { get }`  
- `public System.Collections.Generic.List<System.String> activeFilters { get }`  
- `public System.Action onAvailableFiltersChanged { get; set }`  
- `private Game.UI.Editor.PrefabItem Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.selectedItem { private get; private set }`  
- `private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.items { private get }`  
- `public System.String searchQuery { get; set }`  
- `public System.Boolean searchQueryIsFavorite { get }`  
- `private System.Collections.Generic.IEnumerable<Game.UI.Editor.PopupSearchField+Suggestion> Game.UI.Editor.PopupSearchField.IAdapter.searchSuggestions { private get }`  
- `private System.Int32 Game.UI.Editor.ItemPickerFooter.IAdapter.length { private get }`  
- `public System.Int32 columnCount { get; set }`  

## Constructors

- `public PrefabPickerAdapter()`  

## Methods

- `private <Update>b__40_0(Game.UI.Editor.PrefabItem item) : System.Boolean`  
- `public ClearFilters() : System.Void`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  
- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.Update() : System.Boolean`  
- `private Game.UI.Editor.PopupSearchField.IAdapter.SetFavorite(System.String query, System.Boolean favorite) : System.Void`  
- `private static GetIncompleteTag(System.String[] searchParts) : System.String`  
- `public LoadSettings() : System.Void`  
- `public SelectPrefabByName(System.String name, System.StringComparison comparisonType) : Game.Prefabs.PrefabBase`  
- `public SetPrefabs(System.Collections.Generic.ICollection<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public ToggleFilter(System.String filter, System.Boolean active) : System.Void`  
- `private TryGetDLCBadge(Game.Prefabs.PrefabBase prefab, System.String& icon) : System.Boolean`  
- `public Update() : System.Void`  
- `private UpdateFilteredItems() : System.Void`  

## Nested types

- `Game.UI.Editor.PrefabPickerAdapter+<>c`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass39_0`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass41_0`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass41_1`  

