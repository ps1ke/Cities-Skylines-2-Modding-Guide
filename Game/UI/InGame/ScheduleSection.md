# Game.UI.InGame.ScheduleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ScheduleSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Unity.Entities.Entity m_NightRoutePolicy;
    private Unity.Entities.Entity m_DayRoutePolicy;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Game.UI.InGame.RouteSchedule <schedule>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.RouteSchedule schedule { private get; private set; }

    public ScheduleSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnSetSchedule(System.Int32 newSchedule);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Unity.Entities.Entity m_NightRoutePolicy`  

```csharp
private Unity.Entities.Entity m_NightRoutePolicy;
```

- `private Unity.Entities.Entity m_DayRoutePolicy`  

```csharp
private Unity.Entities.Entity m_DayRoutePolicy;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Game.UI.InGame.RouteSchedule <schedule>k__BackingField`  

```csharp
private Game.UI.InGame.RouteSchedule <schedule>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.RouteSchedule schedule { private get; private set }`  

```csharp
private Game.UI.InGame.RouteSchedule schedule { private get; private set; }
```


## Constructors

- `public ScheduleSection()`  

```csharp
[Preserve]
	public ScheduleSection()
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
		m_PoliciesUISystem = base.World.GetOrCreateSystemManaged<PoliciesUISystem>();
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UITransportConfigurationData>());
		AddBinding(new TriggerBinding<int>(group, "setSchedule", OnSetSchedule));
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		if (!m_ConfigQuery.IsEmptyIgnoreFilter)
		{
			UITransportConfigurationPrefab singletonPrefab = m_PrefabSystem.GetSingletonPrefab<UITransportConfigurationPrefab>(m_ConfigQuery);
			m_DayRoutePolicy = m_PrefabSystem.GetEntity(singletonPrefab.m_DayRoutePolicy);
			m_NightRoutePolicy = m_PrefabSystem.GetEntity(singletonPrefab.m_NightRoutePolicy);
		}
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Route componentData = base.EntityManager.GetComponentData<Route>(selectedEntity);
		schedule = ((!RouteUtils.CheckOption(componentData, RouteOption.Day)) ? (RouteUtils.CheckOption(componentData, RouteOption.Night) ? RouteSchedule.Night : RouteSchedule.DayAndNight) : RouteSchedule.Day);
		base.tooltipTags.Add("TransportLine");
		base.tooltipTags.Add("CargoRoute");
	}
```

- `private OnSetSchedule(System.Int32 newSchedule) : System.Void`  

```csharp
private void OnSetSchedule(int newSchedule)
	{
		switch ((RouteSchedule)newSchedule)
		{
		case RouteSchedule.Day:
			m_PoliciesUISystem.SetPolicy(selectedEntity, m_NightRoutePolicy, active: false);
			m_PoliciesUISystem.SetPolicy(selectedEntity, m_DayRoutePolicy, active: true);
			break;
		case RouteSchedule.Night:
			m_PoliciesUISystem.SetPolicy(selectedEntity, m_NightRoutePolicy, active: true);
			m_PoliciesUISystem.SetPolicy(selectedEntity, m_DayRoutePolicy, active: false);
			break;
		default:
			m_PoliciesUISystem.SetPolicy(selectedEntity, m_NightRoutePolicy, active: false);
			m_PoliciesUISystem.SetPolicy(selectedEntity, m_DayRoutePolicy, active: false);
			break;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("schedule");
		writer.Write((int)schedule);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		schedule = RouteSchedule.DayAndNight;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Route>(selectedEntity) && base.EntityManager.HasComponent<TransportLine>(selectedEntity))
		{
			return base.EntityManager.HasComponent<RouteWaypoint>(selectedEntity);
		}
		return false;
	}
```


