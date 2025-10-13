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
public int AddElement()
	{
		int num = adapter.AddElement();
		ShowElement(num);
		return num;
	}
```

- `private CalculateChildIndices(System.Int32 pageIndex, System.Int32 length, System.Int32& childStartIndex, System.Int32& childEndIndex) : System.Void`  

```csharp
private void CalculateChildIndices(int pageIndex, int length, out int childStartIndex, out int childEndIndex)
	{
		childStartIndex = pageIndex * pageSize;
		childEndIndex = Mathf.Min((pageIndex + 1) * pageSize, length);
	}
```

- `private CalculateIndices(System.Int32 elementIndex, System.Int32 length, System.Int32& pageIndex, System.Int32& childStartIndex, System.Int32& childEndIndex) : System.Void`  

```csharp
private void CalculateIndices(int elementIndex, int length, out int pageIndex, out int childStartIndex, out int childEndIndex)
	{
		pageIndex = Mathf.Min(elementIndex / pageSize, Math.Max(0, (length + pageSize - 1) / pageSize - 1));
		CalculateChildIndices(pageIndex, length, out childStartIndex, out childEndIndex);
	}
```

- `public Clear() : System.Void`  

```csharp
public void Clear()
	{
		adapter.Clear();
	}
```

- `public DeleteElement(System.Int32 index) : System.Void`  

```csharp
public void DeleteElement(int index)
	{
		adapter.DeleteElement(index);
	}
```

- `private DisableChildren(Game.UI.Widgets.IWidget child) : System.Void`  

```csharp
private void DisableChildren(IWidget child)
	{
		if (child is IDisableCallback disableCallback)
		{
			disableCallback.disabled = () => true;
		}
		if (!(child is IContainerWidget containerWidget))
		{
			return;
		}
		foreach (IWidget child2 in containerWidget.children)
		{
			DisableChildren(child2);
		}
	}
```

- `public DuplicateElement(System.Int32 index) : System.Int32`  

```csharp
public int DuplicateElement(int index)
	{
		int num = adapter.DuplicateElement(index);
		ShowElement(num);
		return num;
	}
```

- `public InsertElement(System.Int32 index) : System.Void`  

```csharp
public void InsertElement(int index)
	{
		adapter.InsertElement(index);
	}
```

- `public MoveElement(System.Int32 fromIndex, System.Int32 toIndex) : System.Void`  

```csharp
public void MoveElement(int fromIndex, int toIndex)
	{
		adapter.MoveElement(fromIndex, toIndex);
	}
```

- `private ShowElement(System.Int32 elementIndex) : System.Void`  

```csharp
private void ShowElement(int elementIndex)
	{
		if (elementIndex != -1)
		{
			CalculateIndices(elementIndex, adapter.length, out m_CurrentPageIndex, out m_ChildStartIndex, out m_ChildEndIndex);
		}
	}
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		int length = adapter.length;
		if (length != m_Length)
		{
			widgetChanges |= WidgetChanges.Properties;
			m_Length = length;
		}
		CalculateIndices(m_ChildStartIndex, m_Length, out var pageIndex, out var childStartIndex, out var childEndIndex);
		if (pageIndex != m_CurrentPageIndex || childStartIndex != m_ChildStartIndex || childEndIndex != m_ChildEndIndex)
		{
			widgetChanges |= WidgetChanges.Properties;
			m_CurrentPageIndex = pageIndex;
			m_ChildStartIndex = childStartIndex;
			m_ChildEndIndex = childEndIndex;
		}
		if (adapter.UpdateRange(m_ChildStartIndex, m_ChildEndIndex))
		{
			if (m_Expanded)
			{
				widgetChanges |= WidgetChanges.Children;
			}
			m_Children.Clear();
			m_Children.AddRange(adapter.BuildElementsInRange());
			Assert.AreEqual(m_ChildEndIndex - m_ChildStartIndex, m_Children.Count);
			if (m_Disabled)
			{
				foreach (IWidget child in m_Children)
				{
					DisableChildren(child);
				}
			}
		}
		return widgetChanges;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("expanded");
		writer.Write(expanded);
		writer.PropertyName("resizable");
		writer.Write(adapter.resizable);
		writer.PropertyName("sortable");
		writer.Write(adapter.sortable);
		writer.PropertyName("length");
		writer.Write(m_Length);
		writer.PropertyName("currentPageIndex");
		writer.Write(currentPageIndex);
		writer.PropertyName("pageCount");
		writer.Write(pageCount);
		writer.PropertyName("childStartIndex");
		writer.Write(m_ChildStartIndex);
		writer.PropertyName("childEndIndex");
		writer.Write(m_ChildEndIndex);
	}
```


## Nested types

- `Game.UI.Widgets.PagedList+<>c`  

