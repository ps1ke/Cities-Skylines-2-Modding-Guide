# Game.UI.Widgets.AnimationCurveFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class AnimationCurveFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public AnimationCurveFieldBuilders();

    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public AnimationCurveFieldBuilders()`  

```csharp
public AnimationCurveFieldBuilders();
```


## Methods

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(AnimationCurve))
		{
			return delegate(IValueAccessor accessor)
			{
				if (accessor.GetValue() == null)
				{
					accessor.SetValue(new AnimationCurve());
				}
				return new AnimationCurveField
				{
					accessor = new CastAccessor<AnimationCurve>(accessor)
				};
			};
		}
		return null;
	}
```


## Nested types

- `Game.UI.Widgets.AnimationCurveFieldBuilders+<>c`  

