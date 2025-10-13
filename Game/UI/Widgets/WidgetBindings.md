# Game.UI.Widgets.WidgetBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget>`  

## Code

```csharp
public class WidgetBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget>
{
    private System.String m_Group;
    private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_LastChildren;
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;
    private System.Collections.Generic.List<System.Int32> m_CurrentPath;
    private Colossal.UI.Binding.RawValueBinding m_ChildrenBinding;
    private Game.UI.Widgets.ValueChangedCallback EventValueChanged;

    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
    public System.Boolean active { get; }

    public WidgetBindings(System.String group, System.String name);

    public System.Void AddBindings<U>();
    public System.Void AddBindings(Game.UI.Widgets.IWidgetBindingFactory bindingFactory);
    public System.Void AddDefaultBindings();
    private System.Void Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget>.Read(Colossal.UI.Binding.IJsonReader reader, Game.UI.Widgets.IWidget& value);
    private System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
    public virtual System.Boolean Update();
    private System.Void UpdateChildrenBinding();
    private System.Boolean UpdateSubTree(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> widgets, System.Boolean patch);
    private System.Void WriteChildren(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String m_Group`  

```csharp
private System.String m_Group;
```

- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_LastChildren`  

```csharp
private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_LastChildren;
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;
```

- `private System.Collections.Generic.List<System.Int32> m_CurrentPath`  

```csharp
private System.Collections.Generic.List<System.Int32> m_CurrentPath;
```

- `private Colossal.UI.Binding.RawValueBinding m_ChildrenBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ChildrenBinding;
```

- `private Game.UI.Widgets.ValueChangedCallback EventValueChanged`  

```csharp
private Game.UI.Widgets.ValueChangedCallback EventValueChanged;
```


## Properties

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
```

- `public System.Boolean active { get }`  

```csharp
public System.Boolean active { get; }
```


## Constructors

- `public WidgetBindings(System.String group, System.String name = children)`  

```csharp
public WidgetBindings(string group, string name = "children")
	{
		m_Group = group;
		AddBinding(m_ChildrenBinding = new RawValueBinding(group, name, WriteChildren));
	}
```


## Methods

- `public AddBindings<U>() : System.Void`  

```csharp
public System.Void AddBindings<U>();
```

- `public AddBindings(Game.UI.Widgets.IWidgetBindingFactory bindingFactory) : System.Void`  

```csharp
public void AddBindings(IWidgetBindingFactory bindingFactory)
	{
		foreach (IBinding item in bindingFactory.CreateBindings(m_Group, this, OnValueChanged))
		{
			AddBinding(item);
		}
	}
```

- `public AddDefaultBindings() : System.Void`  

```csharp
public void AddDefaultBindings()
	{
		AddBindings<InvokableBindings>();
		AddBindings<SettableBindings>();
		AddBindings<ExpandableBindings>();
		AddBindings<ListBindings>();
		AddBindings<PagedBindings>();
	}
```

- `private Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget>.Read(Colossal.UI.Binding.IJsonReader reader, Game.UI.Widgets.IWidget& value) : System.Void`  

```csharp
private System.Void Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget>.Read(Colossal.UI.Binding.IJsonReader reader, Game.UI.Widgets.IWidget& value);
```

- `private OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
private void OnValueChanged(IWidget widget)
	{
		UpdateChildrenBinding();
		this.EventValueChanged?.Invoke(widget);
	}
```

- `public virtual Update() : System.Boolean`  

```csharp
public override bool Update()
	{
		UpdateChildrenBinding();
		return base.Update();
	}
```

- `private UpdateChildrenBinding() : System.Void`  

```csharp
private void UpdateChildrenBinding()
	{
		if (active)
		{
			bool flag = !children.SequenceEqual(m_LastChildren);
			if (flag)
			{
				m_LastChildren.Clear();
				m_LastChildren.AddRange(children);
				ContainerExtensions.SetDefaults(m_LastChildren);
			}
			m_CurrentPath.Clear();
			flag |= UpdateSubTree(children, !flag);
			Assert.AreEqual(0, m_CurrentPath.Count);
			if (flag)
			{
				m_ChildrenBinding.Update();
			}
		}
	}
```

- `private UpdateSubTree(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> widgets, System.Boolean patch) : System.Boolean`  

```csharp
private bool UpdateSubTree(IList<IWidget> widgets, bool patch)
	{
		bool result = false;
		for (int i = 0; i < widgets.Count; i++)
		{
			IWidget widget = widgets[i];
			WidgetChanges widgetChanges = widget.Update();
			m_CurrentPath.Add(i);
			if (UpdateSubTree(widget.visibleChildren, patch && (widgetChanges & WidgetChanges.Children) == 0))
			{
				widgetChanges |= WidgetChanges.Children;
			}
			if (widgetChanges != WidgetChanges.None)
			{
				if (patch)
				{
					Widget.PatchWidget(m_ChildrenBinding, m_CurrentPath, widget, widgetChanges);
				}
				else
				{
					result = true;
				}
			}
			m_CurrentPath.RemoveAt(m_CurrentPath.Count - 1);
		}
		return result;
	}
```

- `private WriteChildren(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteChildren(IJsonWriter writer)
	{
		writer.Write((IList<IWidget>)m_LastChildren);
	}
```


## Events

- `EventValueChanged` : `Game.UI.Widgets.ValueChangedCallback`  

```csharp
public event Game.UI.Widgets.ValueChangedCallback EventValueChanged;
```


