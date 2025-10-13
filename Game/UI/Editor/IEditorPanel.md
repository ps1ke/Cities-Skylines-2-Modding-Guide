# Game.UI.Editor.IEditorPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IEditorPanel
{
    public Game.UI.Localization.LocalizedString title { get; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
    public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get; }

    public abstract System.Boolean OnCancel();
    public abstract System.Boolean OnClose();
    public abstract System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
}
```


## Properties

- `public Game.UI.Localization.LocalizedString title { get }`  

```csharp
public Game.UI.Localization.LocalizedString title { get; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
```

- `public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get }`  

```csharp
public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get; }
```


## Methods

- `public abstract OnCancel() : System.Boolean`  

```csharp
public abstract System.Boolean OnCancel();
```

- `public abstract OnClose() : System.Boolean`  

```csharp
public abstract System.Boolean OnClose();
```

- `public abstract OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
public abstract System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
```


