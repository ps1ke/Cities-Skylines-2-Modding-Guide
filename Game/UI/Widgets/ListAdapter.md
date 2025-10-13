# Game.UI.Widgets.ListAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.ListAdapterBase<System.Collections.IList>`  
**Implements:** `Game.UI.Widgets.IListAdapter`  

## Code

```csharp
public class ListAdapter : Game.UI.Widgets.ListAdapterBase<System.Collections.IList>, Game.UI.Widgets.IListAdapter
{
    private System.Type <listType>k__BackingField;

    public System.Type listType { get; set; }

    public ListAdapter();

    public virtual System.Void Clear();
    public virtual System.Void DeleteElement(System.Int32 index);
    public static Game.UI.Widgets.ListAdapter FromList<T>(System.Collections.Generic.List<T> list, Game.UI.Widgets.IEditorGenerator generator);
    public virtual System.Void InsertElement(System.Int32 index);
}
```


## Fields

- `private System.Type <listType>k__BackingField`  

```csharp
private System.Type <listType>k__BackingField;
```


## Properties

- `public System.Type listType { get; set }`  

```csharp
public System.Type listType { get; set; }
```


## Constructors

- `public ListAdapter()`  

```csharp
public ListAdapter();
```


## Methods

- `public virtual Clear() : System.Void`  

```csharp
public override void Clear()
	{
		base.accessor.GetTypedValue()?.Clear();
	}
```

- `public virtual DeleteElement(System.Int32 index) : System.Void`  

```csharp
public override void DeleteElement(int index)
	{
		base.accessor.GetTypedValue().RemoveAt(index);
	}
```

- `public static FromList<T>(System.Collections.Generic.List<T> list, Game.UI.Widgets.IEditorGenerator generator) : Game.UI.Widgets.ListAdapter`  

```csharp
public static Game.UI.Widgets.ListAdapter FromList<T>(System.Collections.Generic.List<T> list, Game.UI.Widgets.IEditorGenerator generator);
```

- `public virtual InsertElement(System.Int32 index) : System.Void`  

```csharp
public override void InsertElement(int index)
	{
		Assert.IsTrue(index >= 0);
		Assert.IsTrue(index <= base.length);
		IList list = base.accessor.GetTypedValue();
		if (list == null)
		{
			list = (IList)ListAdapterBase<IList>.CreateInstance(listType);
			base.accessor.SetTypedValue(list);
		}
		object value = ListAdapterBase<IList>.CreateInstance(base.elementType);
		list.Insert(index, value);
	}
```


## Nested types

- `Game.UI.Widgets.ListAdapter+<>c__DisplayClass7_0<T>`  

