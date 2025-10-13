# Game.UI.Editor.EditorPanelBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public abstract class EditorPanelBase : Game.UI.Editor.IEditorPanel
{
    private Game.UI.Localization.LocalizedString <title>k__BackingField;
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;

    public Game.UI.Localization.LocalizedString title { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
    public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get; }

    protected EditorPanelBase();

    public virtual System.Boolean OnCancel();
    public virtual System.Boolean OnClose();
    public virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
}
```


## Fields

- `private Game.UI.Localization.LocalizedString <title>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <title>k__BackingField;
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;
```


## Properties

- `public Game.UI.Localization.LocalizedString title { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString title { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
```

- `public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get }`  

```csharp
public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get; }
```


## Constructors

- `protected EditorPanelBase()`  

```csharp
protected EditorPanelBase();
```


## Methods

- `public virtual OnCancel() : System.Boolean`  

```csharp
public virtual System.Boolean OnCancel();
```

- `public virtual OnClose() : System.Boolean`  

```csharp
public virtual System.Boolean OnClose();
```

- `public virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
public virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
```


