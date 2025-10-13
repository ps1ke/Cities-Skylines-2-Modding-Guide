# Game.UI.InGame.DistrictsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DistrictsSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityQuery m_DistrictQuery;
    private Unity.Entities.EntityQuery m_DistrictPrefabQuery;
    private Unity.Entities.EntityQuery m_DistrictModifiedQuery;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Selecting;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <districts>k__BackingField;
    private System.Boolean <districtMissing>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> districts { private get; private set; }
    private System.Boolean districtMissing { private get; private set; }

    public DistrictsSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnPreUpdate();
    protected virtual System.Void OnProcess();
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    public System.Void RemoveServiceDistrict(Unity.Entities.Entity district);
    protected virtual System.Void Reset();
    private System.Void ToggleDistrictTool();
    private System.Void ToggleSelectionTool();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  

```csharp
private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictModifiedQuery;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Selecting`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Selecting;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <districts>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <districts>k__BackingField;
```

- `private System.Boolean <districtMissing>k__BackingField`  

```csharp
private System.Boolean <districtMissing>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> districts { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> districts { private get; private set; }
```

- `private System.Boolean districtMissing { private get; private set }`  

```csharp
private System.Boolean districtMissing { private get; private set; }
```


## Constructors

- `public DistrictsSection()`  

```csharp
[Preserve]
	public DistrictsSection()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_AreaToolSystem = base.World.GetOrCreateSystemManaged<AreaToolSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_SelectionToolSystem = base.World.GetOrCreateSystemManaged<SelectionToolSystem>();
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Combine(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
		districts = new NativeList<Entity>(Allocator.Persistent);
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<AreasConfigurationData>());
		m_DistrictQuery = GetEntityQuery(ComponentType.ReadOnly<District>(), ComponentType.Exclude<Temp>());
		m_DistrictPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<DistrictData>(), ComponentType.Exclude<Locked>());
		m_DistrictModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<District>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		AddBinding(new TriggerBinding<Entity>(group, "removeDistrict", RemoveServiceDistrict));
		AddBinding(new TriggerBinding(group, "toggleSelectionTool", ToggleSelectionTool));
		AddBinding(new TriggerBinding(group, "toggleDistrictTool", ToggleDistrictTool));
		AddBinding(m_Selecting = new ValueBinding<bool>(group, "selecting", initialValue: false));
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		districts.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnPreUpdate() : System.Void`  

```csharp
protected override void OnPreUpdate()
	{
		base.OnPreUpdate();
		if (!m_DistrictModifiedQuery.IsEmptyIgnoreFilter)
		{
			RequestUpdate();
		}
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		DynamicBuffer<ServiceDistrict> buffer = base.EntityManager.GetBuffer<ServiceDistrict>(selectedEntity, isReadOnly: true);
		for (int i = 0; i < buffer.Length; i++)
		{
			NativeList<Entity> nativeList = districts;
			ServiceDistrict serviceDistrict = buffer[i];
			nativeList.Add(in serviceDistrict.m_District);
		}
	}
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private void OnToolChanged(ToolBaseSystem tool)
	{
		bool flag = tool == m_SelectionToolSystem && m_SelectionToolSystem.selectionType == SelectionType.ServiceDistrict;
		if (m_Selecting.value && !flag)
		{
			m_SelectionToolSystem.selectionOwner = Entity.Null;
			m_SelectionToolSystem.selectionType = SelectionType.None;
		}
		m_Selecting.Update(flag);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
		districtMissing = m_DistrictQuery.IsEmptyIgnoreFilter;
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("districtMissing");
		writer.Write(districtMissing);
		writer.PropertyName("districts");
		writer.ArrayBegin(districts.Length);
		for (int i = 0; i < districts.Length; i++)
		{
			Entity entity = districts[i];
			writer.TypeBegin("selectedInfo.District");
			writer.PropertyName("name");
			m_NameSystem.BindName(writer, entity);
			writer.PropertyName("entity");
			writer.Write(entity);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `public RemoveServiceDistrict(Unity.Entities.Entity district) : System.Void`  

```csharp
public void RemoveServiceDistrict(Entity district)
	{
		DynamicBuffer<ServiceDistrict> buffer = base.EntityManager.GetBuffer<ServiceDistrict>(selectedEntity);
		bool flag = false;
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i].m_District == district)
			{
				buffer.RemoveAt(i);
				flag = true;
			}
		}
		if (flag)
		{
			m_InfoUISystem.RequestUpdate();
		}
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		districts.Clear();
	}
```

- `private ToggleDistrictTool() : System.Void`  

```csharp
private void ToggleDistrictTool()
	{
		if (m_ToolSystem.activeTool == m_AreaToolSystem)
		{
			m_ToolSystem.activeTool = m_DefaultToolSystem;
			return;
		}
		AreasConfigurationPrefab prefab = m_PrefabSystem.GetPrefab<AreasConfigurationPrefab>(m_ConfigQuery.GetSingletonEntity());
		m_AreaToolSystem.prefab = prefab.m_DefaultDistrictPrefab;
		m_ToolSystem.activeTool = m_AreaToolSystem;
	}
```

- `private ToggleSelectionTool() : System.Void`  

```csharp
private void ToggleSelectionTool()
	{
		if (m_ToolSystem.activeTool == m_SelectionToolSystem)
		{
			m_ToolSystem.activeTool = m_DefaultToolSystem;
			return;
		}
		m_SelectionToolSystem.selectionType = SelectionType.ServiceDistrict;
		m_SelectionToolSystem.selectionOwner = selectedEntity;
		m_ToolSystem.activeTool = m_SelectionToolSystem;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<ServiceDistrict>(selectedEntity))
		{
			return !m_DistrictPrefabQuery.IsEmpty;
		}
		return false;
	}
```


