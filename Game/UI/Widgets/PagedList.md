# Game.UI.Widgets.PagedList

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidgetWithTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IExpandable`, `Game.UI.Widgets.IPaged`, `Game.UI.Widgets.IListWidget`, `Game.UI.Widgets.IContainerWidget`  

## Code

```csharp
public class PagedList : Game.UI.Widgets.NamedWidgetWithTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.IExpandable, Game.UI.Widgets.IPaged, Game.UI.Widgets.IListWidget, Game.UI.Widgets.IContainerWidget
{
    private System.Int32 m_Length;
    private System.Int32 m_CurrentPageIndex;
    private System.Int32 m_ChildStartIndex;
    private System.Int32 m_ChildEndIndex;
    private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Children;
    private System.Boolean m_Expanded;
    private Game.UI.Widgets.IListAdapter <adapter>k__BackingField;
    private System.Int32 <level>k__BackingField;
    private System.Int32 <pageSize>k__BackingField;

    public System.Boolean expanded { get; set; }
    public Game.UI.Widgets.IListAdapter adapter { get; set; }
    public System.Int32 level { get; set; }
    public System.Int32 pageSize { get; set; }
    public System.Int32 pageCount { get; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
    public System.Int32 currentPageIndex { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    public PagedList();

    public System.Int32 AddElement();
    private System.Void CalculateChildIndices(System.Int32 pageIndex, System.Int32 length, System.Int32& childStartIndex, System.Int32& childEndIndex);
    private System.Void CalculateIndices(System.Int32 elementIndex, System.Int32 length, System.Int32& pageIndex, System.Int32& childStartIndex, System.Int32& childEndIndex);
    public System.Void Clear();
    public System.Void DeleteElement(System.Int32 index);
    private System.Void DisableChildren(Game.UI.Widgets.IWidget child);
    public System.Int32 DuplicateElement(System.Int32 index);
    public System.Void InsertElement(System.Int32 index);
    public System.Void MoveElement(System.Int32 fromIndex, System.Int32 toIndex);
    private System.Void ShowElement(System.Int32 elementIndex);
    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Int32 m_Length`  

```csharp
private System.Int32 m_Length;
```

- `private System.Int32 m_CurrentPageIndex`  

```csharp
private System.Int32 m_CurrentPageIndex;
```

- `private System.Int32 m_ChildStartIndex`  

```csharp
private System.Int32 m_ChildStartIndex;
```

- `private System.Int32 m_ChildEndIndex`  

```csharp
private System.Int32 m_ChildEndIndex;
```

- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Children`  

```csharp
private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Children;
```

- `private System.Boolean m_Expanded`  

```csharp
private System.Boolean m_Expanded;
```

- `private Game.UI.Widgets.IListAdapter <adapter>k__BackingField`  

```csharp
private Game.UI.Widgets.IListAdapter <adapter>k__BackingField;
```

- `private System.Int32 <level>k__BackingField`  

```csharp
private System.Int32 <level>k__BackingField;
```

- `private System.Int32 <pageSize>k__BackingField`  

```csharp
private System.Int32 <pageSize>k__BackingField;
```


## Properties

- `public System.Boolean expanded { get; set }`  

```csharp
public System.Boolean expanded { get; set; }
```

- `public Game.UI.Widgets.IListAdapter adapter { get; set }`  

```csharp
public Game.UI.Widgets.IListAdapter adapter { get; set; }
```

- `public System.Int32 level { get; set }`  

```csharp
public System.Int32 level { get; set; }
```

- `public System.Int32 pageSize { get; set }`  

```csharp
public System.Int32 pageSize { get; set; }
```

- `public System.Int32 pageCount { get }`  

```csharp
public System.Int32 pageCount { get; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
```

- `public System.Int32 currentPageIndex { get; set }`  

```csharp
public System.Int32 currentPageIndex { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```


## Constructors

- `public PagedList()`  

```csharp
public PagedList();
```


## Methods

- `public AddElement() : System.Int32`  

```csharp
public System.Int32 AddElement();
```

- `private CalculateChildIndices(System.Int32 pageIndex, System.Int32 length, System.Int32& childStartIndex, System.Int32& childEndIndex) : System.Void`  

```csharp
private System.Void CalculateChildIndices(System.Int32 pageIndex, System.Int32 length, System.Int32& childStartIndex, System.Int32& childEndIndex);
```

- `private CalculateIndices(System.Int32 elementIndex, System.Int32 length, System.Int32& pageIndex, System.Int32& childStartIndex, System.Int32& childEndIndex) : System.Void`  

```csharp
private System.Void CalculateIndices(System.Int32 elementIndex, System.Int32 length, System.Int32& pageIndex, System.Int32& childStartIndex, System.Int32& childEndIndex);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public DeleteElement(System.Int32 index) : System.Void`  

```csharp
public System.Void DeleteElement(System.Int32 index);
```

- `private DisableChildren(Game.UI.Widgets.IWidget child) : System.Void`  

```csharp
private System.Void DisableChildren(Game.UI.Widgets.IWidget child);
```

- `public DuplicateElement(System.Int32 index) : System.Int32`  

```csharp
public System.Int32 DuplicateElement(System.Int32 index);
```

- `public InsertElement(System.Int32 index) : System.Void`  

```csharp
public System.Void InsertElement(System.Int32 index);
```

- `public MoveElement(System.Int32 fromIndex, System.Int32 toIndex) : System.Void`  

```csharp
public System.Void MoveElement(System.Int32 fromIndex, System.Int32 toIndex);
```

- `private ShowElement(System.Int32 elementIndex) : System.Void`  

```csharp
private System.Void ShowElement(System.Int32 elementIndex);
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Widgets.PagedList+<>c`  

