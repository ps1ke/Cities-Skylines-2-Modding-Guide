# Game.UI.Editor.DirectoryAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>`, `Game.UI.Editor.SearchField+IAdapter`  

## Code

```csharp
public class DirectoryAdapter : Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>, Game.UI.Editor.SearchField+IAdapter
{
    private Game.UI.Editor.DirectoryPanelBase m_Panel;
    private Game.UI.Editor.Item m_SelectedItem;
    private System.Collections.Generic.List<Game.UI.Editor.Item> m_Items;
    private System.Boolean m_Dirty;
    private System.Collections.Generic.HashSet<System.String> m_FavoriteIds;
    public System.String searchQuery;
    private System.String m_SearchQuery;
    private System.String <directoryPath>k__BackingField;

    public System.String directoryPath { get; set; }
    public Game.UI.Editor.Item selectedItem { get; set; }
    public System.Collections.Generic.List<Game.UI.Editor.Item> items { get; set; }
    private System.Int32 Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.columnCount { private get; }
    private System.String Game.UI.Editor.SearchField.IAdapter.searchQuery { private get; private set; }

    public DirectoryAdapter(Game.UI.Editor.DirectoryPanelBase panel);

    private System.Boolean <get_items>b__16_0(Game.UI.Editor.Item item);
    private System.Void Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite);
    private System.Boolean Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.Update();
}
```


## Fields

- `private Game.UI.Editor.DirectoryPanelBase m_Panel`  

```csharp
private Game.UI.Editor.DirectoryPanelBase m_Panel;
```

- `private Game.UI.Editor.Item m_SelectedItem`  

```csharp
private Game.UI.Editor.Item m_SelectedItem;
```

- `private System.Collections.Generic.List<Game.UI.Editor.Item> m_Items`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.Item> m_Items;
```

- `private System.Boolean m_Dirty`  

```csharp
private System.Boolean m_Dirty;
```

- `private System.Collections.Generic.HashSet<System.String> m_FavoriteIds`  

```csharp
private System.Collections.Generic.HashSet<System.String> m_FavoriteIds;
```

- `public System.String searchQuery`  

```csharp
public System.String searchQuery;
```

- `private System.String m_SearchQuery`  

```csharp
private System.String m_SearchQuery;
```

- `private System.String <directoryPath>k__BackingField`  

```csharp
private System.String <directoryPath>k__BackingField;
```


## Properties

- `public System.String directoryPath { get; set }`  

```csharp
public System.String directoryPath { get; set; }
```

- `public Game.UI.Editor.Item selectedItem { get; set }`  

```csharp
public Game.UI.Editor.Item selectedItem { get; set; }
```

- `public System.Collections.Generic.List<Game.UI.Editor.Item> items { get; set }`  

```csharp
public System.Collections.Generic.List<Game.UI.Editor.Item> items { get; set; }
```

- `private System.Int32 Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.columnCount { private get }`  

```csharp
private System.Int32 Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.columnCount { private get; }
```

- `private System.String Game.UI.Editor.SearchField.IAdapter.searchQuery { private get; private set }`  

```csharp
private System.String Game.UI.Editor.SearchField.IAdapter.searchQuery { private get; private set; }
```


## Constructors

- `public DirectoryAdapter(Game.UI.Editor.DirectoryPanelBase panel)`  

```csharp
public DirectoryAdapter(Game.UI.Editor.DirectoryPanelBase panel);
```


## Methods

- `private <get_items>b__16_0(Game.UI.Editor.Item item) : System.Boolean`  

```csharp
private System.Boolean <get_items>b__16_0(Game.UI.Editor.Item item);
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  

```csharp
private System.Void Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.SetFavorite(System.Int32 index, System.Boolean favorite);
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.Update() : System.Boolean`  

```csharp
private System.Boolean Game.UI.Editor.ItemPicker<Game.UI.Editor.Item>.IAdapter.Update();
```


