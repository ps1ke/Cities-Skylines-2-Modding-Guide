# Game.UI.Widgets.ArrayAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.ListAdapterBase<System.Array>`  
**Implements:** `Game.UI.Widgets.IListAdapter`  

## Code

```csharp
public class ArrayAdapter : Game.UI.Widgets.ListAdapterBase<System.Array>, Game.UI.Widgets.IListAdapter
{
    public ArrayAdapter();

    public virtual System.Void Clear();
    public virtual System.Void DeleteElement(System.Int32 index);
    public virtual System.Void InsertElement(System.Int32 index);
}
```


## Constructors

- `public ArrayAdapter()`  

```csharp
public ArrayAdapter();
```


## Methods

- `public virtual Clear() : System.Void`  

```csharp
public override void Clear()
	{
		Array typedValue = Array.CreateInstance(base.elementType, 0);
		base.accessor.SetTypedValue(typedValue);
	}
```

- `public virtual DeleteElement(System.Int32 index) : System.Void`  

```csharp
public override void DeleteElement(int index)
	{
		Array typedValue = base.accessor.GetTypedValue();
		Array array = Array.CreateInstance(base.elementType, typedValue.Length - 1);
		Array.Copy(typedValue, 0, array, 0, index);
		Array.Copy(typedValue, index + 1, array, index, typedValue.Length - index - 1);
		base.accessor.SetTypedValue(array);
	}
```

- `public virtual InsertElement(System.Int32 index) : System.Void`  

```csharp
public override void InsertElement(int index)
	{
		Assert.IsTrue(index >= 0);
		Assert.IsTrue(index <= base.length);
		Array typedValue = base.accessor.GetTypedValue();
		object value = ListAdapterBase<Array>.CreateInstance(base.elementType);
		Array array = Array.CreateInstance(base.elementType, base.length + 1);
		array.SetValue(value, index);
		if (typedValue != null)
		{
			Array.Copy(typedValue, array, index);
			Array.Copy(typedValue, index, array, index + 1, typedValue.Length - index);
		}
		base.accessor.SetTypedValue(array);
	}
```


