# Game.UI.Widgets.CustomFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class CustomFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public static readonly System.Collections.Generic.Dictionary<System.Type, Game.UI.Widgets.IFieldBuilderFactory> kFactoryCache;

    public CustomFieldBuilders();

    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Fields

- `public static readonly System.Collections.Generic.Dictionary<System.Type, Game.UI.Widgets.IFieldBuilderFactory> kFactoryCache`  

```csharp
public static readonly System.Collections.Generic.Dictionary<System.Type, Game.UI.Widgets.IFieldBuilderFactory> kFactoryCache;
```


## Constructors

- `public CustomFieldBuilders()`  

```csharp
public CustomFieldBuilders();
```


## Methods

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		Type customFieldFactory = WidgetAttributeUtils.GetCustomFieldFactory(attributes);
		if (customFieldFactory != null)
		{
			if (!kFactoryCache.TryGetValue(customFieldFactory, out var value))
			{
				if (typeof(IFieldBuilderFactory).IsAssignableFrom(customFieldFactory))
				{
					try
					{
						value = (IFieldBuilderFactory)Activator.CreateInstance(customFieldFactory);
					}
					catch (Exception exception)
					{
						UnityEngine.Debug.LogException(exception);
						value = null;
					}
					kFactoryCache[customFieldFactory] = value;
				}
				else
				{
					UnityEngine.Debug.LogError($"{customFieldFactory} is not assignable to IFieldBuilderFactory");
				}
			}
			if (value != null)
			{
				return value.TryCreate(memberType, attributes);
			}
		}
		return null;
	}
```


