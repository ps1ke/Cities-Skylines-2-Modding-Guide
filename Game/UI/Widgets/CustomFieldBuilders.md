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
public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
```


