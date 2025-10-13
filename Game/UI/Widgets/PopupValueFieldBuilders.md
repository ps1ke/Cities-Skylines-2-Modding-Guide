# Game.UI.Widgets.PopupValueFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class PopupValueFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public PopupValueFieldBuilders();

    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public PopupValueFieldBuilders()`  

```csharp
public PopupValueFieldBuilders();
```


## Methods

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (typeof(PrefabBase).IsAssignableFrom(memberType))
		{
			return delegate(IValueAccessor accessor)
			{
				CastAccessor<PrefabBase> accessor2 = new CastAccessor<PrefabBase>(accessor);
				return new PopupValueField<PrefabBase>
				{
					accessor = accessor2,
					popup = new PrefabPickerPopup(memberType)
				};
			};
		}
		return null;
	}
```


## Nested types

- `Game.UI.Widgets.PopupValueFieldBuilders+<>c__DisplayClass0_0`  

