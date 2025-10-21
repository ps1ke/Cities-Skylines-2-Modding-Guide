# Game.UI.Editor.PrefabPickerAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>`, `Game.UI.Editor.PopupSearchField+IAdapter`, `Game.UI.Editor.SearchField+IAdapter`, `Game.UI.Editor.ItemPickerFooter+IAdapter`, `Game.UI.Editor.FilterMenu+IAdapter`  

## Code

```csharp
public class PrefabPickerAdapter : Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>, Game.UI.Editor.PopupSearchField+IAdapter, Game.UI.Editor.SearchField+IAdapter, Game.UI.Editor.ItemPickerFooter+IAdapter, Game.UI.Editor.FilterMenu+IAdapter
{
    private System.Boolean <displayPrefabTypeTooltip>k__BackingField;
    private Game.UI.ImageSystem m_ImageSystem;
    private System.String m_SearchQuery;
    private System.Boolean m_SearchQueryIsFavorite;
    private System.Boolean m_SearchQueryChanged;
    private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> m_Items;
    private System.Boolean m_ItemsChanged;
    private System.Collections.Generic.List<System.String> m_AvailableFilters;
    private System.Collections.Generic.List<System.String> m_ActiveFilters;
    private System.Boolean m_ActiveFiltersChanged;
    private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> m_FilteredItems;
    private System.Boolean m_FilteredItemsChanged;
    private Game.UI.Editor.PrefabItem m_SelectedItem;
    private Game.Prefabs.PrefabBase m_SelectedPrefab;
    private System.Collections.Generic.List<System.String> m_SearchHistory;
    private System.Collections.Generic.HashSet<System.String> m_SearchFavorites;
    private System.Collections.Generic.List<Game.UI.Editor.PopupSearchField+Suggestion> m_SearchSuggestions;
    private System.Collections.Generic.HashSet<System.String> m_FavoriteIds;
    private System.Int32 m_ColumnCount;
    private System.Action <onAvailableFiltersChanged>k__BackingField;
    public System.Action<Game.Prefabs.PrefabBase> EventPrefabSelected;
    public static const System.Int32 kMaxHistoryLength;
    public static const System.Int32 kMaxHistoryDisplayLength;

    public System.Boolean displayPrefabTypeTooltip { get; set; }
    public Game.Prefabs.PrefabBase selectedPrefab { get; set; }
    public System.Collections.Generic.List<System.String> availableFilters { get; }
    public System.Collections.Generic.List<System.String> activeFilters { get; }
    public System.Action onAvailableFiltersChanged { get; set; }
    private Game.UI.Editor.PrefabItem Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.selectedItem { private get; private set; }
    private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.items { private get; }
    public System.String searchQuery { get; set; }
    public System.Boolean searchQueryIsFavorite { get; }
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.PopupSearchField+Suggestion> Game.UI.Editor.PopupSearchField.IAdapter.searchSuggestions { private get; }
    private System.Int32 Game.UI.Editor.ItemPickerFooter.IAdapter.length { private get; }
    public System.Int32 columnCount { get; set; }

    public PrefabPickerAdapter();

    private System.Boolean <Update>b__40_0(Game.UI.Editor.PrefabItem item);
    public System.Void ClearFilters();
    private System.Void Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite);
    private System.Boolean Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.Update();
    private System.Void Game.UI.Editor.PopupSearchField.IAdapter.SetFavorite(System.String query, System.Boolean favorite);
    private static System.String GetIncompleteTag(System.String[] searchParts);
    public System.Void LoadSettings();
    public Game.Prefabs.PrefabBase SelectPrefabByName(System.String name, System.StringComparison comparisonType);
    public System.Void SetPrefabs(System.Collections.Generic.ICollection<Game.Prefabs.PrefabBase> prefabs);
    public System.Void ToggleFilter(System.String filter, System.Boolean active);
    private System.Boolean TryGetDLCBadge(Game.Prefabs.PrefabBase prefab, System.String& icon);
    public System.Void Update();
    private System.Void UpdateFilteredItems();
}
```


## Fields

- `private System.Boolean <displayPrefabTypeTooltip>k__BackingField`  

```csharp
private System.Boolean <displayPrefabTypeTooltip>k__BackingField;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private System.String m_SearchQuery`  

```csharp
private System.String m_SearchQuery;
```

- `private System.Boolean m_SearchQueryIsFavorite`  

```csharp
private System.Boolean m_SearchQueryIsFavorite;
```

- `private System.Boolean m_SearchQueryChanged`  

```csharp
private System.Boolean m_SearchQueryChanged;
```

- `private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> m_Items`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> m_Items;
```

- `private System.Boolean m_ItemsChanged`  

```csharp
private System.Boolean m_ItemsChanged;
```

- `private System.Collections.Generic.List<System.String> m_AvailableFilters`  

```csharp
private System.Collections.Generic.List<System.String> m_AvailableFilters;
```

- `private System.Collections.Generic.List<System.String> m_ActiveFilters`  

```csharp
private System.Collections.Generic.List<System.String> m_ActiveFilters;
```

- `private System.Boolean m_ActiveFiltersChanged`  

```csharp
private System.Boolean m_ActiveFiltersChanged;
```

- `private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> m_FilteredItems`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> m_FilteredItems;
```

- `private System.Boolean m_FilteredItemsChanged`  

```csharp
private System.Boolean m_FilteredItemsChanged;
```

- `private Game.UI.Editor.PrefabItem m_SelectedItem`  

```csharp
private Game.UI.Editor.PrefabItem m_SelectedItem;
```

- `private Game.Prefabs.PrefabBase m_SelectedPrefab`  

```csharp
private Game.Prefabs.PrefabBase m_SelectedPrefab;
```

- `private System.Collections.Generic.List<System.String> m_SearchHistory`  

```csharp
private System.Collections.Generic.List<System.String> m_SearchHistory;
```

- `private System.Collections.Generic.HashSet<System.String> m_SearchFavorites`  

```csharp
private System.Collections.Generic.HashSet<System.String> m_SearchFavorites;
```

- `private System.Collections.Generic.List<Game.UI.Editor.PopupSearchField+Suggestion> m_SearchSuggestions`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.PopupSearchField+Suggestion> m_SearchSuggestions;
```

- `private System.Collections.Generic.HashSet<System.String> m_FavoriteIds`  

```csharp
private System.Collections.Generic.HashSet<System.String> m_FavoriteIds;
```

- `private System.Int32 m_ColumnCount`  

```csharp
private System.Int32 m_ColumnCount;
```

- `private System.Action <onAvailableFiltersChanged>k__BackingField`  

```csharp
private System.Action <onAvailableFiltersChanged>k__BackingField;
```

- `public System.Action<Game.Prefabs.PrefabBase> EventPrefabSelected`  

```csharp
public System.Action<Game.Prefabs.PrefabBase> EventPrefabSelected;
```

- `public static const System.Int32 kMaxHistoryLength`  

```csharp
public static const System.Int32 kMaxHistoryLength;
```

- `public static const System.Int32 kMaxHistoryDisplayLength`  

```csharp
public static const System.Int32 kMaxHistoryDisplayLength;
```


## Properties

- `public System.Boolean displayPrefabTypeTooltip { get; set }`  

```csharp
public System.Boolean displayPrefabTypeTooltip { get; set; }
```

- `public Game.Prefabs.PrefabBase selectedPrefab { get; set }`  

```csharp
public Game.Prefabs.PrefabBase selectedPrefab { get; set; }
```

- `public System.Collections.Generic.List<System.String> availableFilters { get }`  

```csharp
public System.Collections.Generic.List<System.String> availableFilters { get; }
```

- `public System.Collections.Generic.List<System.String> activeFilters { get }`  

```csharp
public System.Collections.Generic.List<System.String> activeFilters { get; }
```

- `public System.Action onAvailableFiltersChanged { get; set }`  

```csharp
public System.Action onAvailableFiltersChanged { get; set; }
```

- `private Game.UI.Editor.PrefabItem Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.selectedItem { private get; private set }`  

```csharp
private Game.UI.Editor.PrefabItem Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.selectedItem { private get; private set; }
```

- `private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.items { private get }`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.PrefabItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.items { private get; }
```

- `public System.String searchQuery { get; set }`  

```csharp
public System.String searchQuery { get; set; }
```

- `public System.Boolean searchQueryIsFavorite { get }`  

```csharp
public System.Boolean searchQueryIsFavorite { get; }
```

- `private System.Collections.Generic.IEnumerable<Game.UI.Editor.PopupSearchField+Suggestion> Game.UI.Editor.PopupSearchField.IAdapter.searchSuggestions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.PopupSearchField+Suggestion> Game.UI.Editor.PopupSearchField.IAdapter.searchSuggestions { private get; }
```

- `private System.Int32 Game.UI.Editor.ItemPickerFooter.IAdapter.length { private get }`  

```csharp
private System.Int32 Game.UI.Editor.ItemPickerFooter.IAdapter.length { private get; }
```

- `public System.Int32 columnCount { get; set }`  

```csharp
public System.Int32 columnCount { get; set; }
```


## Constructors

- `public PrefabPickerAdapter()`  

```csharp
public PrefabPickerAdapter();
```


## Methods

- `private <Update>b__40_0(Game.UI.Editor.PrefabItem item) : System.Boolean`  

```csharp
private System.Boolean <Update>b__40_0(Game.UI.Editor.PrefabItem item);
```

- `public ClearFilters() : System.Void`  

```csharp
public System.Void ClearFilters();
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  

```csharp
private System.Void Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite);
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.Update() : System.Boolean`  

```csharp
private System.Boolean Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.Update();
```

- `private Game.UI.Editor.PopupSearchField.IAdapter.SetFavorite(System.String query, System.Boolean favorite) : System.Void`  

```csharp
private System.Void Game.UI.Editor.PopupSearchField.IAdapter.SetFavorite(System.String query, System.Boolean favorite);
```

- `private static GetIncompleteTag(System.String[] searchParts) : System.String`  

```csharp
private static System.String GetIncompleteTag(System.String[] searchParts);
```

- `public LoadSettings() : System.Void`  

```csharp
public System.Void LoadSettings();
```

- `public SelectPrefabByName(System.String name, System.StringComparison comparisonType) : Game.Prefabs.PrefabBase`  

```csharp
public Game.Prefabs.PrefabBase SelectPrefabByName(System.String name, System.StringComparison comparisonType);
```

- `public SetPrefabs(System.Collections.Generic.ICollection<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public System.Void SetPrefabs(System.Collections.Generic.ICollection<Game.Prefabs.PrefabBase> prefabs);
```

- `public ToggleFilter(System.String filter, System.Boolean active) : System.Void`  

```csharp
public System.Void ToggleFilter(System.String filter, System.Boolean active);
```

- `private TryGetDLCBadge(Game.Prefabs.PrefabBase prefab, System.String& icon) : System.Boolean`  

```csharp
private System.Boolean TryGetDLCBadge(Game.Prefabs.PrefabBase prefab, System.String& icon);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `private UpdateFilteredItems() : System.Void`  

```csharp
private System.Void UpdateFilteredItems();
```


## Nested types

- `Game.UI.Editor.PrefabPickerAdapter+<>c`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass39_0`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass41_0`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass41_1`  

