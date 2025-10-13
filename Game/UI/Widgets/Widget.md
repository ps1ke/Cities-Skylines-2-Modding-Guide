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
protected virtual WidgetChanges Update()
	{
		return WidgetChanges.None;
	}
```

- `private Game.UI.Widgets.IWidget.WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual void WriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("tutorialTag");
		writer.Write(tutorialTag);
	}
```

- `public static PatchWidget(Colossal.UI.Binding.RawValueBinding binding, System.Collections.Generic.IList<System.Int32> path, Game.UI.Widgets.IWidget widget, Game.UI.Widgets.WidgetChanges changes) : System.Void`  

```csharp
public static void PatchWidget(RawValueBinding binding, IList<int> path, IWidget widget, WidgetChanges changes)
	{
		IJsonWriter jsonWriter = binding.PatchBegin();
		if (changes == WidgetChanges.Path)
		{
			WritePatchPath(jsonWriter, path, "path");
			jsonWriter.Write(widget.path);
		}
		else if ((changes & WidgetChanges.TotalProperties) != WidgetChanges.None && (changes & ~WidgetChanges.TotalProperties) == 0)
		{
			WritePatchPath(jsonWriter, path, "props");
			jsonWriter.TypeBegin(widget.propertiesTypeName);
			widget.WriteProperties(jsonWriter);
			jsonWriter.TypeEnd();
		}
		else if (changes == WidgetChanges.Children)
		{
			WritePatchPath(jsonWriter, path, "children");
			jsonWriter.Write(widget.visibleChildren);
		}
		else
		{
			WritePatchPath(jsonWriter, path);
			jsonWriter.Write(widget);
		}
		binding.PatchEnd();
	}
```

- `public SetChildrenChanged() : System.Void`  

```csharp
public void SetChildrenChanged()
	{
		m_Changes |= WidgetChanges.Children;
	}
```

- `public SetPropertiesChanged() : System.Void`  

```csharp
public void SetPropertiesChanged()
	{
		m_Changes |= WidgetChanges.Properties;
	}
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual WidgetChanges Update()
	{
		return WidgetChanges.None;
	}
```

- `private UpdateBase() : Game.UI.Widgets.WidgetChanges`  

```csharp
private WidgetChanges UpdateBase()
	{
		UpdateVisibility();
		WidgetChanges widgetChanges = m_Changes;
		m_Changes = WidgetChanges.None;
		if (m_Hidden && !m_IsInitialUpdate)
		{
			return widgetChanges;
		}
		m_IsInitialUpdate = false;
		bool flag = disabled != null && disabled();
		if (flag != m_Disabled)
		{
			widgetChanges |= WidgetChanges.Activity;
			m_Disabled = flag;
		}
		return widgetChanges | Update();
	}
```

- `public virtual UpdateVisibility() : Game.UI.Widgets.WidgetChanges`  

```csharp
public virtual WidgetChanges UpdateVisibility()
	{
		bool flag = hidden != null && hidden();
		if (flag != m_Hidden)
		{
			m_Hidden = flag;
			m_Changes |= WidgetChanges.Visibility;
			return WidgetChanges.Visibility;
		}
		return WidgetChanges.None;
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(typeof(Widget).FullName);
		writer.PropertyName("path");
		writer.Write(path);
		writer.PropertyName("props");
		writer.TypeBegin(propertiesTypeName);
		WriteBaseProperties(writer);
		writer.TypeEnd();
		writer.PropertyName("children");
		writer.Write(visibleChildren);
		writer.TypeEnd();
	}
```

- `private WriteBaseProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteBaseProperties(IJsonWriter writer)
	{
		writer.PropertyName("disabled");
		writer.Write(m_Disabled);
		writer.PropertyName("hidden");
		writer.Write(m_Hidden);
		WriteProperties(writer);
	}
```

- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path) : System.Void`  

```csharp
public static void WritePatchPath(IJsonWriter writer, IList<int> path, string propertyName1, string propertyName2, string propertyName3, int propertyName4)
	{
		writer.ArrayBegin(2 * path.Count + 3);
		for (int i = 0; i < path.Count - 1; i++)
		{
			writer.Write(path[i]);
			writer.Write("children");
		}
		writer.Write(path[path.Count - 1]);
		writer.Write(propertyName1);
		writer.Write(propertyName2);
		writer.Write(propertyName3);
		writer.Write(propertyName4);
		writer.ArrayEnd();
	}
```

- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName) : System.Void`  

```csharp
public static void WritePatchPath(IJsonWriter writer, IList<int> path, string propertyName1, string propertyName2, string propertyName3, int propertyName4)
	{
		writer.ArrayBegin(2 * path.Count + 3);
		for (int i = 0; i < path.Count - 1; i++)
		{
			writer.Write(path[i]);
			writer.Write("children");
		}
		writer.Write(path[path.Count - 1]);
		writer.Write(propertyName1);
		writer.Write(propertyName2);
		writer.Write(propertyName3);
		writer.Write(propertyName4);
		writer.ArrayEnd();
	}
```

- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName1, System.String propertyName2, System.String propertyName3, System.Int32 propertyName4) : System.Void`  

```csharp
public static void WritePatchPath(IJsonWriter writer, IList<int> path, string propertyName1, string propertyName2, string propertyName3, int propertyName4)
	{
		writer.ArrayBegin(2 * path.Count + 3);
		for (int i = 0; i < path.Count - 1; i++)
		{
			writer.Write(path[i]);
			writer.Write("children");
		}
		writer.Write(path[path.Count - 1]);
		writer.Write(propertyName1);
		writer.Write(propertyName2);
		writer.Write(propertyName3);
		writer.Write(propertyName4);
		writer.ArrayEnd();
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual void WriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("tutorialTag");
		writer.Write(tutorialTag);
	}
```


