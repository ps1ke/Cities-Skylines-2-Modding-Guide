# Game.UI.InGame.PhotoModeUISystem+Tab

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Tab
{
    private System.String <id>k__BackingField;
    private System.String <icon>k__BackingField;
    private System.Collections.Generic.List<Game.UI.Widgets.IWidget> <items>k__BackingField;

    public System.String id { get; set; }
    public System.String icon { get; set; }
    public System.Collections.Generic.List<Game.UI.Widgets.IWidget> items { get; set; }

    public Tab();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <id>k__BackingField`  

```csharp
private System.String <id>k__BackingField;
```

- `private System.String <icon>k__BackingField`  

```csharp
private System.String <icon>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> <items>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.Widgets.IWidget> <items>k__BackingField;
```


## Properties

- `public System.String id { get; set }`  

```csharp
public System.String id { get; set; }
```

- `public System.String icon { get; set }`  

```csharp
public System.String icon { get; set; }
```

- `public System.Collections.Generic.List<Game.UI.Widgets.IWidget> items { get; set }`  

```csharp
public System.Collections.Generic.List<Game.UI.Widgets.IWidget> items { get; set; }
```


## Constructors

- `public Tab()`  

```csharp
public Tab();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


