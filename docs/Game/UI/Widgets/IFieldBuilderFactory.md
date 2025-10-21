# Game.UI.Widgets.IFieldBuilderFactory

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IFieldBuilderFactory
{
    public abstract Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Methods

- `public abstract TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public abstract Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
```


