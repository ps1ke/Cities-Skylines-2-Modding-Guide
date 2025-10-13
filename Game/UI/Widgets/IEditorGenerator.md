# Game.UI.Widgets.IEditorGenerator

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IEditorGenerator
{
    public abstract Game.UI.Widgets.IWidget Build(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path);
}
```


## Methods

- `public abstract Build(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path) : Game.UI.Widgets.IWidget`  

```csharp
public abstract Game.UI.Widgets.IWidget Build(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path);
```


