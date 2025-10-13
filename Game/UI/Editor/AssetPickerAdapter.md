# Game.UI.Editor.AssetPickerAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>`, `Game.UI.Editor.SearchField+IAdapter`, `Game.UI.Editor.ItemPickerFooter+IAdapter`  

## Code

```csharp
public class AssetPickerAdapter : Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>, Game.UI.Editor.SearchField+IAdapter, Game.UI.Editor.ItemPickerFooter+IAdapter
{
    private System.String m_SearchQuery;
    private System.Collections.Generic.List<Game.UI.Editor.AssetItem> m_Items;
    private System.Collections.Generic.List<Game.UI.Editor.AssetItem> m_FilteredItems;
    private System.Boolean m_FilteredItemsChanged;
    private Game.UI.Editor.AssetItem m_SelectedItem;
    private System.Int32 m_ColumnCount;
    private System.Boolean m_UseGlobalColumnCount;
    private System.Collections.Generic.HashSet<System.String> m_FavoriteIds;
    public System.Action<Game.UI.Editor.AssetItem> EventItemSelected;

    public Game.UI.Editor.AssetItem selectedItem { get; set; }
    private Game.UI.Editor.AssetItem Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.selectedItem { private get; private set; }
    private System.Collections.Generic.List<Game.UI.Editor.AssetItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.items { private get; }
    public System.String searchQuery { get; set; }
    private System.Int32 Game.UI.Editor.ItemPickerFooter.IAdapter.length { private get; }
    public System.Int32 columnCount { get; set; }

    public AssetPickerAdapter(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, System.Int32 columnCount);

    private System.Boolean <UpdateFilteredItems>b__16_0(Game.UI.Editor.AssetItem item);
    private System.Void Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite);
    private System.Boolean Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.Update();
    public Game.UI.Editor.AssetItem SelectItemByGuid(Colossal.Hash128 guid);
    public Game.UI.Editor.AssetItem SelectItemByName(System.String name, System.StringComparison comparisonType);
    public System.Void SetItems(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items);
    private System.Void UpdateFilteredItems();
}
```


## Fields

- `private System.String m_SearchQuery`  

```csharp
private System.String m_SearchQuery;
```

- `private System.Collections.Generic.List<Game.UI.Editor.AssetItem> m_Items`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.AssetItem> m_Items;
```

- `private System.Collections.Generic.List<Game.UI.Editor.AssetItem> m_FilteredItems`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.AssetItem> m_FilteredItems;
```

- `private System.Boolean m_FilteredItemsChanged`  

```csharp
private System.Boolean m_FilteredItemsChanged;
```

- `private Game.UI.Editor.AssetItem m_SelectedItem`  

```csharp
private Game.UI.Editor.AssetItem m_SelectedItem;
```

- `private System.Int32 m_ColumnCount`  

```csharp
private System.Int32 m_ColumnCount;
```

- `private System.Boolean m_UseGlobalColumnCount`  

```csharp
private System.Boolean m_UseGlobalColumnCount;
```

- `private System.Collections.Generic.HashSet<System.String> m_FavoriteIds`  

```csharp
private System.Collections.Generic.HashSet<System.String> m_FavoriteIds;
```

- `public System.Action<Game.UI.Editor.AssetItem> EventItemSelected`  

```csharp
public System.Action<Game.UI.Editor.AssetItem> EventItemSelected;
```


## Properties

- `public Game.UI.Editor.AssetItem selectedItem { get; set }`  

```csharp
public Game.UI.Editor.AssetItem selectedItem { get; set; }
```

- `private Game.UI.Editor.AssetItem Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.selectedItem { private get; private set }`  

```csharp
private Game.UI.Editor.AssetItem Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.selectedItem { private get; private set; }
```

- `private System.Collections.Generic.List<Game.UI.Editor.AssetItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.items { private get }`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.AssetItem> Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.items { private get; }
```

- `public System.String searchQuery { get; set }`  

```csharp
public System.String searchQuery { get; set; }
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

- `public AssetPickerAdapter(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, System.Int32 columnCount = 0)`  

```csharp
public AssetPickerAdapter(IEnumerable<AssetItem> items, int columnCount = 0)
	{
		m_FavoriteIds.Clear();
		EditorSettings editorSettings = SharedSettings.instance?.editor;
		if (editorSettings.assetPickerFavorites != null)
		{
			string[] assetPickerFavorites = editorSettings.assetPickerFavorites;
			foreach (string item in assetPickerFavorites)
			{
				m_FavoriteIds.Add(item);
			}
		}
		SetItems(items);
		m_UseGlobalColumnCount = columnCount <= 0;
		if (m_UseGlobalColumnCount)
		{
			m_ColumnCount = editorSettings?.assetPickerColumnCount ?? 4;
		}
		else
		{
			m_ColumnCount = columnCount;
		}
	}
```


## Methods

- `private <UpdateFilteredItems>b__16_0(Game.UI.Editor.AssetItem item) : System.Boolean`  

```csharp
private System.Boolean <UpdateFilteredItems>b__16_0(Game.UI.Editor.AssetItem item);
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  

```csharp
private System.Void Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite);
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.Update() : System.Boolean`  

```csharp
private System.Boolean Game.UI.Editor.ItemPicker<Game.UI.Editor.AssetItem>.IAdapter.Update();
```

- `public SelectItemByGuid(Colossal.Hash128 guid) : Game.UI.Editor.AssetItem`  

```csharp
public AssetItem SelectItemByGuid(Hash128 guid)
	{
		m_SelectedItem = m_Items.FirstOrDefault((AssetItem item) => item.guid == guid);
		return m_SelectedItem;
	}
```

- `public SelectItemByName(System.String name, System.StringComparison comparisonType) : Game.UI.Editor.AssetItem`  

```csharp
public AssetItem SelectItemByName(string name, StringComparison comparisonType)
	{
		m_SelectedItem = m_Items.FirstOrDefault((AssetItem item) => item.fileName.Equals(name, comparisonType));
		return m_SelectedItem;
	}
```

- `public SetItems(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items) : System.Void`  

```csharp
public void SetItems(IEnumerable<AssetItem> items)
	{
		m_Items = items.ToList();
		foreach (AssetItem item in m_Items)
		{
			item.favorite = m_FavoriteIds.Contains(item.guid.ToString());
		}
		m_Items.Sort();
		m_FilteredItems = new List<AssetItem>(m_Items);
	}
```

- `private UpdateFilteredItems() : System.Void`  

```csharp
private void UpdateFilteredItems()
	{
		m_FilteredItems.Clear();
		List<AssetItem> filteredItems = m_FilteredItems;
		IEnumerable<AssetItem> collection;
		if (string.IsNullOrEmpty(m_SearchQuery))
		{
			IEnumerable<AssetItem> items = m_Items;
			collection = items;
		}
		else
		{
			collection = m_Items.Where((AssetItem item) => !string.IsNullOrEmpty(item.fileName) && item.fileName.IndexOf(m_SearchQuery, StringComparison.OrdinalIgnoreCase) != -1);
		}
		filteredItems.AddRange(collection);
		m_FilteredItemsChanged = true;
	}
```


## Nested types

- `Game.UI.Editor.AssetPickerAdapter+<>c__DisplayClass14_0`  
- `Game.UI.Editor.AssetPickerAdapter+<>c__DisplayClass15_0`  

