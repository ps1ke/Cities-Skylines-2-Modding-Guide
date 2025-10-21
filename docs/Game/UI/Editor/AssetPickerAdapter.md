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
public AssetPickerAdapter(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items, System.Int32 columnCount);
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
public Game.UI.Editor.AssetItem SelectItemByGuid(Colossal.Hash128 guid);
```

- `public SelectItemByName(System.String name, System.StringComparison comparisonType) : Game.UI.Editor.AssetItem`  

```csharp
public Game.UI.Editor.AssetItem SelectItemByName(System.String name, System.StringComparison comparisonType);
```

- `public SetItems(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items) : System.Void`  

```csharp
public System.Void SetItems(System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> items);
```

- `private UpdateFilteredItems() : System.Void`  

```csharp
private System.Void UpdateFilteredItems();
```


## Nested types

- `Game.UI.Editor.AssetPickerAdapter+<>c__DisplayClass14_0`  
- `Game.UI.Editor.AssetPickerAdapter+<>c__DisplayClass15_0`  

