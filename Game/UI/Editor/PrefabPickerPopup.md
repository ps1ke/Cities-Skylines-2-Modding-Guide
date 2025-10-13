# Game.UI.Editor.PrefabPickerPopup

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IValueFieldPopup<Game.Prefabs.PrefabBase>`  

## Code

```csharp
public class PrefabPickerPopup : Game.UI.Widgets.IValueFieldPopup<Game.Prefabs.PrefabBase>
{
    private Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> m_Accessor;
    private System.Type m_PrefabType;
    private System.Func<Game.Prefabs.PrefabBase, System.Boolean> m_Filter;
    private System.Boolean <nullable>k__BackingField;
    private Game.UI.Editor.PrefabPickerAdapter m_Adapter;
    private readonly System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;

    public System.Boolean nullable { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }

    public PrefabPickerPopup(System.Type prefabType, System.Func<Game.Prefabs.PrefabBase, System.Boolean> filter);

    public System.Void Attach(Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> accessor);
    public System.Void Detach();
    public Game.UI.Localization.LocalizedString GetDisplayValue(Game.Prefabs.PrefabBase value);
    private System.Void OnPrefabSelected(Game.Prefabs.PrefabBase prefab);
    public System.Boolean Update();
}
```


## Fields

- `private Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> m_Accessor`  

```csharp
private Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> m_Accessor;
```

- `private System.Type m_PrefabType`  

```csharp
private System.Type m_PrefabType;
```

- `private System.Func<Game.Prefabs.PrefabBase, System.Boolean> m_Filter`  

```csharp
private System.Func<Game.Prefabs.PrefabBase, System.Boolean> m_Filter;
```

- `private System.Boolean <nullable>k__BackingField`  

```csharp
private System.Boolean <nullable>k__BackingField;
```

- `private Game.UI.Editor.PrefabPickerAdapter m_Adapter`  

```csharp
private Game.UI.Editor.PrefabPickerAdapter m_Adapter;
```

- `private readonly System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

```csharp
private readonly System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;
```


## Properties

- `public System.Boolean nullable { get; set }`  

```csharp
public System.Boolean nullable { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
```


## Constructors

- `public PrefabPickerPopup(System.Type prefabType, System.Func<Game.Prefabs.PrefabBase, System.Boolean> filter = null)`  

```csharp
public PrefabPickerPopup(Type prefabType, Func<PrefabBase, bool> filter = null)
	{
		m_PrefabType = prefabType;
		m_Filter = filter;
		m_Adapter = new PrefabPickerAdapter();
		PrefabPickerAdapter adapter = m_Adapter;
		adapter.EventPrefabSelected = (Action<PrefabBase>)Delegate.Combine(adapter.EventPrefabSelected, new Action<PrefabBase>(OnPrefabSelected));
		children = new IWidget[3]
		{
			new PopupSearchField
			{
				adapter = m_Adapter,
				hasFavorites = true
			},
			new ItemPicker<PrefabItem>
			{
				adapter = m_Adapter,
				hasFavorites = true,
				hasImages = true
			},
			new ItemPickerFooter
			{
				adapter = m_Adapter
			}
		};
		ContainerExtensions.SetDefaults(children);
	}
```


## Methods

- `public Attach(Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> accessor) : System.Void`  

```csharp
public void Attach(ITypedValueAccessor<PrefabBase> accessor)
	{
		m_Accessor = accessor;
		List<PrefabBase> list = new List<PrefabBase>();
		if (nullable)
		{
			list.Add(null);
		}
		PrefabSystem prefabSystem = World.DefaultGameObjectInjectionWorld?.GetExistingSystemManaged<PrefabSystem>();
		if (prefabSystem != null)
		{
			foreach (PrefabBase prefab in prefabSystem.prefabs)
			{
				if (m_PrefabType.IsInstanceOfType(prefab) && (m_Filter == null || m_Filter(prefab)))
				{
					list.Add(prefab);
				}
			}
		}
		m_Adapter.SetPrefabs(list);
		m_Adapter.LoadSettings();
	}
```

- `public Detach() : System.Void`  

```csharp
public void Detach()
	{
		m_Adapter.searchQuery = string.Empty;
		m_Adapter.SetPrefabs(Array.Empty<PrefabBase>());
	}
```

- `public GetDisplayValue(Game.Prefabs.PrefabBase value) : Game.UI.Localization.LocalizedString`  

```csharp
public LocalizedString GetDisplayValue(PrefabBase value)
	{
		return EditorPrefabUtils.GetPrefabLabel(value);
	}
```

- `private OnPrefabSelected(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private void OnPrefabSelected(PrefabBase prefab)
	{
		m_Accessor.SetTypedValue(prefab);
	}
```

- `public Update() : System.Boolean`  

```csharp
public bool Update()
	{
		m_Adapter.selectedPrefab = m_Accessor.GetTypedValue();
		m_Adapter.Update();
		return false;
	}
```


