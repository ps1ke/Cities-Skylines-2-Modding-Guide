# Game.UI.Widgets.ExpandableGroup

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidgetWithTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IExpandable`, `Game.UI.Widgets.IContainerWidget`  

## Code

```csharp
public class ExpandableGroup : Game.UI.Widgets.NamedWidgetWithTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.IExpandable, Game.UI.Widgets.IContainerWidget
{
    private Game.Reflection.ITypedValueAccessor<System.Boolean> m_ExpandedAccessor;
    private System.Boolean m_Expanded;
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;

    public System.Boolean expanded { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    public ExpandableGroup(Game.Reflection.ITypedValueAccessor<System.Boolean> expandedAccessor);
    public ExpandableGroup(System.Boolean expanded);

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.Reflection.ITypedValueAccessor<System.Boolean> m_ExpandedAccessor`  

```csharp
private Game.Reflection.ITypedValueAccessor<System.Boolean> m_ExpandedAccessor;
```

- `private System.Boolean m_Expanded`  

```csharp
private System.Boolean m_Expanded;
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;
```


## Properties

- `public System.Boolean expanded { get; set }`  

```csharp
public System.Boolean expanded { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```


## Constructors

- `public ExpandableGroup(Game.Reflection.ITypedValueAccessor<System.Boolean> expandedAccessor)`  

```csharp
public ExpandableGroup(bool expanded = false)
	{
		m_ExpandedAccessor = new ObjectAccessor<bool>(expanded, readOnly: false);
		m_Expanded = expanded;
	}
```

- `public ExpandableGroup(System.Boolean expanded = False)`  

```csharp
public ExpandableGroup(bool expanded = false)
	{
		m_ExpandedAccessor = new ObjectAccessor<bool>(expanded, readOnly: false);
		m_Expanded = expanded;
	}
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		bool typedValue = m_ExpandedAccessor.GetTypedValue();
		if (typedValue != m_Expanded)
		{
			widgetChanges |= WidgetChanges.Properties | WidgetChanges.Children;
			m_Expanded = typedValue;
		}
		return widgetChanges;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("expanded");
		writer.Write(expanded);
	}
```


