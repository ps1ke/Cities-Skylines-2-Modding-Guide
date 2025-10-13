# Game.UI.Editor.EditorSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.ExpandableGroup`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IExpandable`, `Game.UI.Widgets.IContainerWidget`  

## Code

```csharp
public class EditorSection : Game.UI.Widgets.ExpandableGroup, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.IExpandable, Game.UI.Widgets.IContainerWidget
{
    private System.Action <onDelete>k__BackingField;
    private System.Boolean m_Active;
    private Game.Reflection.ITypedValueAccessor<System.Boolean> <active>k__BackingField;
    private System.Boolean <primary>k__BackingField;
    private System.Nullable<UnityEngine.Color> m_Color;
    public static readonly UnityEngine.Color kPrefabColor;

    public System.Action onDelete { get; set; }
    public Game.Reflection.ITypedValueAccessor<System.Boolean> active { get; set; }
    public System.Boolean primary { get; set; }
    public System.Nullable<UnityEngine.Color> color { get; set; }

    public EditorSection();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Action <onDelete>k__BackingField`  

```csharp
private System.Action <onDelete>k__BackingField;
```

- `private System.Boolean m_Active`  

```csharp
private System.Boolean m_Active;
```

- `private Game.Reflection.ITypedValueAccessor<System.Boolean> <active>k__BackingField`  

```csharp
private Game.Reflection.ITypedValueAccessor<System.Boolean> <active>k__BackingField;
```

- `private System.Boolean <primary>k__BackingField`  

```csharp
private System.Boolean <primary>k__BackingField;
```

- `private System.Nullable<UnityEngine.Color> m_Color`  

```csharp
private System.Nullable<UnityEngine.Color> m_Color;
```

- `public static readonly UnityEngine.Color kPrefabColor`  

```csharp
public static readonly UnityEngine.Color kPrefabColor;
```


## Properties

- `public System.Action onDelete { get; set }`  

```csharp
public System.Action onDelete { get; set; }
```

- `public Game.Reflection.ITypedValueAccessor<System.Boolean> active { get; set }`  

```csharp
public Game.Reflection.ITypedValueAccessor<System.Boolean> active { get; set; }
```

- `public System.Boolean primary { get; set }`  

```csharp
public System.Boolean primary { get; set; }
```

- `public System.Nullable<UnityEngine.Color> color { get; set }`  

```csharp
public System.Nullable<UnityEngine.Color> color { get; set; }
```


## Constructors

- `public EditorSection()`  

```csharp
public EditorSection();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		bool flag = active?.GetTypedValue() ?? true;
		if (flag != m_Active)
		{
			widgetChanges |= WidgetChanges.Properties;
			m_Active = flag;
		}
		return widgetChanges;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("expandable");
		writer.Write(base.children.Count != 0);
		writer.PropertyName("deletable");
		writer.Write(onDelete != null);
		writer.PropertyName("activatable");
		writer.Write(active != null);
		writer.PropertyName("active");
		writer.Write(m_Active);
		writer.PropertyName("primary");
		writer.Write(primary);
		writer.PropertyName("color");
		if (color.HasValue)
		{
			writer.Write(color.Value);
		}
		else
		{
			writer.WriteNull();
		}
	}
```


## Nested types

- `Game.UI.Editor.EditorSection+Bindings`  

