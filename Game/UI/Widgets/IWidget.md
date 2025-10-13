# Game.UI.Widgets.IWidget

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** interface abstract public  

**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract interface IWidget : Colossal.UI.Binding.IJsonWritable
{
    public Game.UI.Widgets.PathSegment path { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
    public System.String propertiesTypeName { get; }

    public abstract Game.UI.Widgets.WidgetChanges Update();
    public abstract System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Properties

- `public Game.UI.Widgets.PathSegment path { get; set }`  

```csharp
public Game.UI.Widgets.PathSegment path { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```

- `public System.String propertiesTypeName { get }`  

```csharp
public System.String propertiesTypeName { get; }
```


## Methods

- `public abstract Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
public abstract Game.UI.Widgets.WidgetChanges Update();
```

- `public abstract WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public abstract System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


