# Game.UI.Widgets.Widget

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public abstract class Widget : Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Game.UI.Widgets.WidgetChanges m_Changes;
    private Game.UI.Widgets.PathSegment m_Path;
    private System.String m_TutorialTag;
    protected System.Boolean m_Disabled;
    protected System.Boolean m_Hidden;
    private System.Boolean m_IsInitialUpdate;
    private System.Func<System.Boolean> <disabled>k__BackingField;
    private System.Func<System.Boolean> <hidden>k__BackingField;
    protected static const System.String kProperties;
    protected static const System.String kChildren;
    protected static const System.String kTutorialTag;

    public Game.UI.Widgets.PathSegment path { get; set; }
    public System.String tutorialTag { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
    public System.Func<System.Boolean> disabled { get; set; }
    public System.Func<System.Boolean> hidden { get; set; }
    public System.Boolean isVisible { get; }
    public System.Boolean isActive { get; }
    public System.String propertiesTypeName { get; }

    protected Widget();

    private Game.UI.Widgets.WidgetChanges Game.UI.Widgets.IWidget.Update();
    private System.Void Game.UI.Widgets.IWidget.WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    public static System.Void PatchWidget(Colossal.UI.Binding.RawValueBinding binding, System.Collections.Generic.IList<System.Int32> path, Game.UI.Widgets.IWidget widget, Game.UI.Widgets.WidgetChanges changes);
    public System.Void SetChildrenChanged();
    public System.Void SetPropertiesChanged();
    protected virtual Game.UI.Widgets.WidgetChanges Update();
    private Game.UI.Widgets.WidgetChanges UpdateBase();
    public virtual Game.UI.Widgets.WidgetChanges UpdateVisibility();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteBaseProperties(Colossal.UI.Binding.IJsonWriter writer);
    public static System.Void WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path);
    public static System.Void WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName);
    public static System.Void WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName1, System.String propertyName2, System.String propertyName3, System.Int32 propertyName4);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.UI.Widgets.WidgetChanges m_Changes`  

```csharp
private Game.UI.Widgets.WidgetChanges m_Changes;
```

- `private Game.UI.Widgets.PathSegment m_Path`  

```csharp
private Game.UI.Widgets.PathSegment m_Path;
```

- `private System.String m_TutorialTag`  

```csharp
private System.String m_TutorialTag;
```

- `protected System.Boolean m_Disabled`  

```csharp
protected System.Boolean m_Disabled;
```

- `protected System.Boolean m_Hidden`  

```csharp
protected System.Boolean m_Hidden;
```

- `private System.Boolean m_IsInitialUpdate`  

```csharp
private System.Boolean m_IsInitialUpdate;
```

- `private System.Func<System.Boolean> <disabled>k__BackingField`  

```csharp
private System.Func<System.Boolean> <disabled>k__BackingField;
```

- `private System.Func<System.Boolean> <hidden>k__BackingField`  

```csharp
private System.Func<System.Boolean> <hidden>k__BackingField;
```

- `protected static const System.String kProperties`  

```csharp
protected static const System.String kProperties;
```

- `protected static const System.String kChildren`  

```csharp
protected static const System.String kChildren;
```

- `protected static const System.String kTutorialTag`  

```csharp
protected static const System.String kTutorialTag;
```


## Properties

- `public Game.UI.Widgets.PathSegment path { get; set }`  

```csharp
public Game.UI.Widgets.PathSegment path { get; set; }
```

- `public System.String tutorialTag { get; set }`  

```csharp
public System.String tutorialTag { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```

- `public System.Func<System.Boolean> disabled { get; set }`  

```csharp
public System.Func<System.Boolean> disabled { get; set; }
```

- `public System.Func<System.Boolean> hidden { get; set }`  

```csharp
public System.Func<System.Boolean> hidden { get; set; }
```

- `public System.Boolean isVisible { get }`  

```csharp
public System.Boolean isVisible { get; }
```

- `public System.Boolean isActive { get }`  

```csharp
public System.Boolean isActive { get; }
```

- `public System.String propertiesTypeName { get }`  

```csharp
public System.String propertiesTypeName { get; }
```


## Constructors

- `protected Widget()`  

```csharp
protected Widget();
```


## Methods

- `private Game.UI.Widgets.IWidget.Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
private Game.UI.Widgets.WidgetChanges Game.UI.Widgets.IWidget.Update();
```

- `private Game.UI.Widgets.IWidget.WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void Game.UI.Widgets.IWidget.WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `public static PatchWidget(Colossal.UI.Binding.RawValueBinding binding, System.Collections.Generic.IList<System.Int32> path, Game.UI.Widgets.IWidget widget, Game.UI.Widgets.WidgetChanges changes) : System.Void`  

```csharp
public static System.Void PatchWidget(Colossal.UI.Binding.RawValueBinding binding, System.Collections.Generic.IList<System.Int32> path, Game.UI.Widgets.IWidget widget, Game.UI.Widgets.WidgetChanges changes);
```

- `public SetChildrenChanged() : System.Void`  

```csharp
public System.Void SetChildrenChanged();
```

- `public SetPropertiesChanged() : System.Void`  

```csharp
public System.Void SetPropertiesChanged();
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `private UpdateBase() : Game.UI.Widgets.WidgetChanges`  

```csharp
private Game.UI.Widgets.WidgetChanges UpdateBase();
```

- `public virtual UpdateVisibility() : Game.UI.Widgets.WidgetChanges`  

```csharp
public virtual Game.UI.Widgets.WidgetChanges UpdateVisibility();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteBaseProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteBaseProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path) : System.Void`  

```csharp
public static System.Void WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path);
```

- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName) : System.Void`  

```csharp
public static System.Void WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName);
```

- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName1, System.String propertyName2, System.String propertyName3, System.Int32 propertyName4) : System.Void`  

```csharp
public static System.Void WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName1, System.String propertyName2, System.String propertyName3, System.Int32 propertyName4);
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


