# Game.UI.Widgets.ContainerExtensions

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class ContainerExtensions
{
    public static Game.UI.Widgets.IWidget FindChild(Game.UI.Widgets.IWidget widget, Game.UI.Widgets.PathSegment path);
    public static T FindChild<T>(System.Collections.Generic.IEnumerable<T> children, Game.UI.Widgets.PathSegment path);
    public static System.Void SetDefaults<T>(System.Collections.Generic.IList<T> children);
}
```


## Methods

- `public static FindChild(Game.UI.Widgets.IWidget widget, Game.UI.Widgets.PathSegment path) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget FindChild(Game.UI.Widgets.IWidget widget, Game.UI.Widgets.PathSegment path);
```

- `public static FindChild<T>(System.Collections.Generic.IEnumerable<T> children, Game.UI.Widgets.PathSegment path) : T`  

```csharp
public static T FindChild<T>(System.Collections.Generic.IEnumerable<T> children, Game.UI.Widgets.PathSegment path);
```

- `public static SetDefaults<T>(System.Collections.Generic.IList<T> children) : System.Void`  

```csharp
public static System.Void SetDefaults<T>(System.Collections.Generic.IList<T> children);
```


