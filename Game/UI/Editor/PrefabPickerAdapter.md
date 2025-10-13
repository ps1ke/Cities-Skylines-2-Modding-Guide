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
public void ClearFilters()
	{
		m_ActiveFilters.Clear();
		m_ActiveFiltersChanged = true;
	}
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  

```csharp
private System.Void Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite);
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.PrefabItem>.IAdapter.Update() : System.Boolean`  

```csharp
public void Update()
	{
		if (m_SelectedPrefab != m_SelectedItem?.prefab)
		{
			m_SelectedItem = m_Items.FirstOrDefault((PrefabItem item) => item.prefab == m_SelectedPrefab);
		}
		if (m_ItemsChanged || m_SearchQueryChanged || m_ActiveFiltersChanged)
		{
			m_ItemsChanged = false;
			m_SearchQueryChanged = false;
			m_ActiveFiltersChanged = false;
			UpdateFilteredItems();
		}
	}
```

- `private Game.UI.Editor.PopupSearchField.IAdapter.SetFavorite(System.String query, System.Boolean favorite) : System.Void`  

```csharp
private System.Void Game.UI.Editor.PopupSearchField.IAdapter.SetFavorite(System.String query, System.Boolean favorite);
```

- `private static GetIncompleteTag(System.String[] searchParts) : System.String`  

```csharp
[CanBeNull]
	private static string GetIncompleteTag(string[] searchParts)
	{
		if (searchParts.Length == 0)
		{
			return null;
		}
		string text = searchParts[^1];
		if (text.Length <= 1 || !text.StartsWith("#"))
		{
			return null;
		}
		return text.Substring(1);
	}
```

- `public LoadSettings() : System.Void`  

```csharp
public void LoadSettings()
	{
		m_SearchHistory.Clear();
		m_SearchFavorites.Clear();
		m_ColumnCount = 1;
		m_FavoriteIds.Clear();
		EditorSettings editorSettings = SharedSettings.instance?.editor;
		if (editorSettings == null)
		{
			return;
		}
		if (editorSettings.prefabPickerSearchHistory != null)
		{
			m_SearchHistory.AddRange(editorSettings.prefabPickerSearchHistory);
		}
		if (editorSettings.prefabPickerSearchFavorites != null)
		{
			string[] prefabPickerSearchFavorites = editorSettings.prefabPickerSearchFavorites;
			foreach (string item in prefabPickerSearchFavorites)
			{
				m_SearchFavorites.Add(item);
			}
		}
		m_ColumnCount = editorSettings.prefabPickerColumnCount;
		if (editorSettings.prefabPickerFavorites != null)
		{
			string[] prefabPickerSearchFavorites = editorSettings.prefabPickerFavorites;
			foreach (string item2 in prefabPickerSearchFavorites)
			{
				m_FavoriteIds.Add(item2);
			}
		}
	}
```

- `public SelectPrefabByName(System.String name, System.StringComparison comparisonType) : Game.Prefabs.PrefabBase`  

```csharp
public PrefabBase SelectPrefabByName(string name, StringComparison comparisonType)
	{
		m_SelectedPrefab = m_Items.Select((PrefabItem item) => item.prefab).FirstOrDefault((PrefabBase prefab) => prefab.name.Equals(name, comparisonType));
		return m_SelectedPrefab;
	}
```

- `public SetPrefabs(System.Collections.Generic.ICollection<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public void SetPrefabs([ItemCanBeNull] ICollection<PrefabBase> prefabs)
	{
		m_Items.Clear();
		m_Items.Capacity = prefabs.Count;
		m_ItemsChanged = true;
		m_SelectedItem = null;
		m_AvailableFilters.Clear();
		m_ActiveFilters.Clear();
		HashSet<string> hashSet = new HashSet<string>();
		foreach (PrefabBase prefab in prefabs)
		{
			string prefabID = EditorPrefabUtils.GetPrefabID(prefab);
			PrefabItem prefabItem = new PrefabItem
			{
				prefab = prefab,
				displayName = EditorPrefabUtils.GetPrefabLabel(prefab)
			};
			if (prefab != null && displayPrefabTypeTooltip)
			{
				prefabItem.tooltip = LocalizedString.Value(prefab.GetType().Name);
			}
			if (prefab != null)
			{
				prefabItem.tags.AddRange(EditorPrefabUtils.GetPrefabTags(prefab.GetType()));
				foreach (ComponentBase component in prefab.components)
				{
					prefabItem.tags.Add(component.GetType().Name.ToLowerInvariant());
				}
				foreach (string tag in prefabItem.tags)
				{
					hashSet.Add(tag);
				}
				prefabItem.image = ImageSystem.GetThumbnail(prefab);
				if (TryGetDLCBadge(prefab, out var icon))
				{
					prefabItem.badge = icon;
				}
			}
			if (prefabID != null)
			{
				prefabItem.favorite = m_FavoriteIds.Contains(prefabID);
			}
			m_Items.Add(prefabItem);
		}
		m_AvailableFilters.AddRange(hashSet);
		m_AvailableFilters.Sort();
		onAvailableFiltersChanged?.Invoke();
		m_Items.Sort();
	}
```

- `public ToggleFilter(System.String filter, System.Boolean active) : System.Void`  

```csharp
public void ToggleFilter(string filter, bool active)
	{
		if (active)
		{
			if (!m_ActiveFilters.Contains(filter))
			{
				m_ActiveFilters.Add(filter);
			}
		}
		else
		{
			m_ActiveFilters.Remove(filter);
		}
		m_ActiveFiltersChanged = true;
	}
```

- `private TryGetDLCBadge(Game.Prefabs.PrefabBase prefab, System.String& icon) : System.Boolean`  

```csharp
private bool TryGetDLCBadge(PrefabBase prefab, out string icon)
	{
		if (prefab.TryGet<AssetPackItem>(out var component) && component.m_Packs != null)
		{
			AssetPackPrefab[] packs = component.m_Packs;
			for (int i = 0; i < packs.Length; i++)
			{
				if (packs[i].TryGet<UIObject>(out var component2) && !string.IsNullOrEmpty(component2.m_Icon))
				{
					icon = component2.m_Icon;
					return true;
				}
			}
		}
		if (prefab.TryGet<ContentPrerequisite>(out var component3))
		{
			ContentPrefab contentPrerequisite = component3.m_ContentPrerequisite;
			if (contentPrerequisite.TryGet<UIObject>(out var component4) && !string.IsNullOrEmpty(component4.m_Icon))
			{
				icon = component4.m_Icon;
				return true;
			}
			if (contentPrerequisite.TryGet<DlcRequirement>(out var component5))
			{
				string dlcName = PlatformManager.instance.GetDlcName(component5.m_Dlc);
				if (!string.IsNullOrEmpty(dlcName))
				{
					icon = "Media/DLC/" + dlcName + ".svg";
					return true;
				}
			}
		}
		icon = null;
		return false;
	}
```

- `public Update() : System.Void`  

```csharp
public void Update()
	{
		if (m_SelectedPrefab != m_SelectedItem?.prefab)
		{
			m_SelectedItem = m_Items.FirstOrDefault((PrefabItem item) => item.prefab == m_SelectedPrefab);
		}
		if (m_ItemsChanged || m_SearchQueryChanged || m_ActiveFiltersChanged)
		{
			m_ItemsChanged = false;
			m_SearchQueryChanged = false;
			m_ActiveFiltersChanged = false;
			UpdateFilteredItems();
		}
	}
```

- `private UpdateFilteredItems() : System.Void`  

```csharp
private void UpdateFilteredItems()
	{
		m_SearchSuggestions.Clear();
		m_FilteredItems.Clear();
		m_FilteredItemsChanged = true;
		string[] array = m_SearchQuery.Split(' ');
		string[] words = array.Where((string p) => p.Length > 0 && !p.StartsWith("#")).ToArray();
		string[] tags = (from p in array.Take(array.Length - 1)
			where p.Length > 1 && p.StartsWith("#")
			select p.Substring(1)).Concat(m_ActiveFilters).ToArray();
		string incompleteTag = GetIncompleteTag(array);
		if (words.Length != 0 || tags.Length != 0 || incompleteTag != null)
		{
			m_SearchSuggestions.AddRange(m_SearchHistory.Where((string s) => !m_SearchFavorites.Contains(s) && s.StartsWith(m_SearchQuery, StringComparison.OrdinalIgnoreCase)).Take(20).Select(PopupSearchField.Suggestion.NonFavorite));
			m_SearchSuggestions.AddRange(m_SearchFavorites.Where((string s) => s.StartsWith(m_SearchQuery, StringComparison.OrdinalIgnoreCase)).Select(PopupSearchField.Suggestion.Favorite));
			m_FilteredItems.AddRange(m_Items.Where(delegate(PrefabItem item)
			{
				if (item.prefab == null)
				{
					return false;
				}
				bool num = words.Length == 0 || words.All((string word) => item.prefab.name.IndexOf(word, StringComparison.OrdinalIgnoreCase) != -1);
				string typeName = item.prefab.GetType().Name;
				bool flag = words.Any((string word) => word.IndexOf(typeName, StringComparison.OrdinalIgnoreCase) != -1);
				bool flag2 = tags.Length == 0 || tags.Any((string tag) => item.tags.Contains(tag, StringComparer.OrdinalIgnoreCase));
				bool flag3 = incompleteTag == null || item.tags.Any((string tag) => tag.StartsWith(incompleteTag, StringComparison.OrdinalIgnoreCase));
				return ((num || flag) && flag2 && flag3) ? true : false;
			}));
		}
		else
		{
			m_SearchSuggestions.AddRange(m_SearchHistory.Where((string s) => !m_SearchFavorites.Contains(s)).Take(20).Select(PopupSearchField.Suggestion.NonFavorite));
			m_SearchSuggestions.AddRange(m_SearchFavorites.Select(PopupSearchField.Suggestion.Favorite));
			m_FilteredItems.AddRange(m_Items);
		}
		m_SearchSuggestions.Sort();
	}
```


## Nested types

- `Game.UI.Editor.PrefabPickerAdapter+<>c`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass39_0`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass41_0`  
- `Game.UI.Editor.PrefabPickerAdapter+<>c__DisplayClass41_1`  

