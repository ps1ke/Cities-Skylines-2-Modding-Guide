# Game.UI.Widgets.BezierFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class BezierFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public BezierFieldBuilders();

    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public BezierFieldBuilders()`  

```csharp
public BezierFieldBuilders();
```


## Methods

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(Bezier4x3))
		{
			return WidgetReflectionUtils.CreateFieldBuilder<Bezier4x3Field, Bezier4x3>();
		}
		return null;
	}
```


