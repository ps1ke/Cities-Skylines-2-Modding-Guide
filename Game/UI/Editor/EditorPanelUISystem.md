# Game.UI.Editor.EditorPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class EditorPanelUISystem : Game.UI.UISystemBase
{
    private Game.UI.Editor.IEditorPanel m_LastPanel;
    private Game.UI.Editor.IEditorPanel <activePanel>k__BackingField;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveBinding;
    private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Localization.LocalizedString>> m_TitleBinding;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public Game.UI.Editor.IEditorPanel activePanel { get; set; }
    private Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { private get; }

    public EditorPanelUISystem();

    private System.Int32 <OnCreate>b__13_0();
    public static System.Void AddEditorWidgetBindings(Game.UI.Widgets.WidgetBindings widgetBindings);
    private System.Void Cancel();
    private System.Void Close();
    private System.Int32 GetWidth();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
    private System.Void SetWidth(System.Int32 width);
}
```


## Fields

- `private Game.UI.Editor.IEditorPanel m_LastPanel`  

```csharp
private Game.UI.Editor.IEditorPanel m_LastPanel;
```

- `private Game.UI.Editor.IEditorPanel <activePanel>k__BackingField`  

```csharp
private Game.UI.Editor.IEditorPanel <activePanel>k__BackingField;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Localization.LocalizedString>> m_TitleBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Localization.LocalizedString>> m_TitleBinding;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `public Game.UI.Editor.IEditorPanel activePanel { get; set }`  

```csharp
public Game.UI.Editor.IEditorPanel activePanel { get; set; }
```

- `private Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { private get }`  

```csharp
private Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { private get; }
```


## Constructors

- `public EditorPanelUISystem()`  

```csharp
public EditorPanelUISystem();
```


## Methods

- `private <OnCreate>b__13_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__13_0();
```

- `public static AddEditorWidgetBindings(Game.UI.Widgets.WidgetBindings widgetBindings) : System.Void`  

```csharp
public static System.Void AddEditorWidgetBindings(Game.UI.Widgets.WidgetBindings widgetBindings);
```

- `private Cancel() : System.Void`  

```csharp
private System.Void Cancel();
```

- `private Close() : System.Void`  

```csharp
private System.Void Close();
```

- `private GetWidth() : System.Int32`  

```csharp
private System.Int32 GetWidth();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
public System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
```

- `private SetWidth(System.Int32 width) : System.Void`  

```csharp
private System.Void SetWidth(System.Int32 width);
```


