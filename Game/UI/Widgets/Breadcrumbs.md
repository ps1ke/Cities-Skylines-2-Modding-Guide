# Game.UI.Widgets.Breadcrumbs

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `System.Collections.Generic.IEnumerable<Game.UI.Widgets.Label>`, `System.Collections.IEnumerable`, `Game.UI.Widgets.IContainerWidget`  

## Code

```csharp
public class Breadcrumbs : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, System.Collections.Generic.IEnumerable<Game.UI.Widgets.Label>, System.Collections.IEnumerable, Game.UI.Widgets.IContainerWidget
{
    private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Labels;

    public System.Int32 labelCount { get; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    public Breadcrumbs();

    public System.Collections.Generic.IEnumerator<Game.UI.Widgets.Label> GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public Game.UI.Widgets.Breadcrumbs WithLabel(Game.UI.Widgets.Label label);
    public Game.UI.Widgets.Breadcrumbs WithOutLabel(Game.UI.Widgets.Label label);
}
```


## Fields

- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Labels`  

```csharp
private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Labels;
```


## Properties

- `public System.Int32 labelCount { get }`  

```csharp
public System.Int32 labelCount { get; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```


## Constructors

- `public Breadcrumbs()`  

```csharp
public Breadcrumbs();
```


## Methods

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Game.UI.Widgets.Label>`  

```csharp
public System.Collections.Generic.IEnumerator<Game.UI.Widgets.Label> GetEnumerator();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public WithLabel(Game.UI.Widgets.Label label) : Game.UI.Widgets.Breadcrumbs`  

```csharp
public Game.UI.Widgets.Breadcrumbs WithLabel(Game.UI.Widgets.Label label);
```

- `public WithOutLabel(Game.UI.Widgets.Label label) : Game.UI.Widgets.Breadcrumbs`  

```csharp
public Game.UI.Widgets.Breadcrumbs WithOutLabel(Game.UI.Widgets.Label label);
```


