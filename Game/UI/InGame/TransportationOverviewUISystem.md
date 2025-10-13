# Game.UI.InGame.TransportationOverviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportationOverviewUISystem : Game.UI.UISystemBase
{
    private Game.UI.NameSystem m_NameSystem;
    private Game.Prefabs.UnlockSystem m_UnlockSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.Entity m_OutOfServicePolicy;
    private Unity.Entities.Entity m_DayRoutePolicy;
    private Unity.Entities.Entity m_NightRoutePolicy;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityQuery m_LineQuery;
    private Unity.Entities.EntityQuery m_ModifiedLineQuery;
    private Unity.Entities.EntityQuery m_UnlockQuery;
    private Unity.Entities.EntityArchetype m_ColorUpdateArchetype;
    private Colossal.UI.Binding.RawValueBinding m_TransportLines;
    private Colossal.UI.Binding.RawValueBinding m_PassengerTypes;
    private Colossal.UI.Binding.RawValueBinding m_CargoTypes;
    private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedCargoType;
    private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedPassengerType;
    private Game.Prefabs.UITransportConfigurationPrefab m_Config;
    private Game.UI.UIUpdateState m_UpdateState;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }

    public TransportationOverviewUISystem();

    private System.Void BindCargoTypes(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindLine(Game.UI.InGame.UITransportLineData lineData, Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindLines(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindPassengerTypes(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindTypes(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UITransportItem[] items);
    private System.Void DeleteLine(Unity.Entities.Entity entity);
    private System.String GetInitialSelectedType();
    public System.Void HideLine(Unity.Entities.Entity entity, System.Boolean showOthers);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void RequestUpdate();
    public System.Void ResetLinesVisibility();
    private System.Void SelectLine(Unity.Entities.Entity entity);
    private System.Void SetLineColor(Unity.Entities.Entity entity, UnityEngine.Color32 color);
    private System.Void SetLineName(Unity.Entities.Entity entity, System.String name);
    private System.Void SetLineSchedule(Unity.Entities.Entity entity, System.Int32 schedule);
    public System.Void SetLineState(Unity.Entities.Entity entity, System.Boolean state);
    private System.Void SetSelectedCargoType(System.String type);
    private System.Void SetSelectedPassengerType(System.String type);
    public System.Void ShowLine(Unity.Entities.Entity entity, System.Boolean hideOthers);
    public System.Void ToggleHighlight(Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  

```csharp
private Game.Prefabs.UnlockSystem m_UnlockSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.Entity m_OutOfServicePolicy`  

```csharp
private Unity.Entities.Entity m_OutOfServicePolicy;
```

- `private Unity.Entities.Entity m_DayRoutePolicy`  

```csharp
private Unity.Entities.Entity m_DayRoutePolicy;
```

- `private Unity.Entities.Entity m_NightRoutePolicy`  

```csharp
private Unity.Entities.Entity m_NightRoutePolicy;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityQuery m_LineQuery`  

```csharp
private Unity.Entities.EntityQuery m_LineQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedLineQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedLineQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockQuery;
```

- `private Unity.Entities.EntityArchetype m_ColorUpdateArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ColorUpdateArchetype;
```

- `private Colossal.UI.Binding.RawValueBinding m_TransportLines`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TransportLines;
```

- `private Colossal.UI.Binding.RawValueBinding m_PassengerTypes`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_PassengerTypes;
```

- `private Colossal.UI.Binding.RawValueBinding m_CargoTypes`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_CargoTypes;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedCargoType`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedCargoType;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedPassengerType`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedPassengerType;
```

- `private Game.Prefabs.UITransportConfigurationPrefab m_Config`  

```csharp
private Game.Prefabs.UITransportConfigurationPrefab m_Config;
```

- `private Game.UI.UIUpdateState m_UpdateState`  

```csharp
private Game.UI.UIUpdateState m_UpdateState;
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


## Constructors

- `public TransportationOverviewUISystem()`  

```csharp
[Preserve]
	public TransportationOverviewUISystem()
	{
	}
```


## Methods

- `private BindCargoTypes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindCargoTypes(IJsonWriter writer)
	{
		BindTypes(writer, m_Config.m_CargoLineTypes);
	}
```

- `private BindLine(Game.UI.InGame.UITransportLineData lineData, Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindLine(UITransportLineData lineData, IJsonWriter binder)
	{
		binder.TypeBegin("Game.UI.InGame.UITransportLine");
		binder.PropertyName("name");
		m_NameSystem.BindName(binder, lineData.entity);
		binder.PropertyName("vkName");
		m_NameSystem.BindNameForVirtualKeyboard(binder, lineData.entity);
		binder.PropertyName("lineData");
		binder.Write(lineData);
		binder.TypeEnd();
	}
```

- `private BindLines(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindLines(IJsonWriter binder)
	{
		NativeArray<UITransportLineData> sortedLines = TransportUIUtils.GetSortedLines(m_LineQuery, base.EntityManager, m_PrefabSystem);
		binder.ArrayBegin(sortedLines.Length);
		for (int i = 0; i < sortedLines.Length; i++)
		{
			BindLine(sortedLines[i], binder);
		}
		binder.ArrayEnd();
	}
```

- `private BindPassengerTypes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindPassengerTypes(IJsonWriter writer)
	{
		BindTypes(writer, m_Config.m_PassengerLineTypes);
	}
```

- `private BindTypes(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UITransportItem[] items) : System.Void`  

```csharp
private void BindTypes(IJsonWriter writer, UITransportItem[] items)
	{
		writer.ArrayBegin(items.Length);
		foreach (UITransportItem uITransportItem in items)
		{
			new UITransportType(m_PrefabSystem.GetEntity(uITransportItem.m_Unlockable), Enum.GetName(typeof(TransportType), uITransportItem.m_Type), uITransportItem.m_Icon, m_UnlockSystem.IsLocked(uITransportItem.m_Unlockable)).Write(m_PrefabUISystem, writer);
		}
		writer.ArrayEnd();
	}
```

- `private DeleteLine(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void DeleteLine(Entity entity)
	{
		if (base.EntityManager.Exists(entity))
		{
			m_EndFrameBarrier.CreateCommandBuffer().AddComponent(entity, default(Deleted));
		}
	}
```

- `private GetInitialSelectedType() : System.String`  

```csharp
private string GetInitialSelectedType()
	{
		UITransportItem[] cargoLineTypes = m_Config.m_CargoLineTypes;
		foreach (UITransportItem uITransportItem in cargoLineTypes)
		{
			if (!m_UnlockSystem.IsLocked(uITransportItem.m_Unlockable))
			{
				return Enum.GetName(typeof(TransportType), uITransportItem.m_Type);
			}
		}
		return Enum.GetName(typeof(TransportType), TransportType.None);
	}
```

- `public HideLine(Unity.Entities.Entity entity, System.Boolean showOthers) : System.Void`  

```csharp
public void HideLine(Entity entity, bool showOthers)
	{
		if (base.EntityManager.Exists(entity))
		{
			EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
			if (showOthers)
			{
				entityCommandBuffer.RemoveComponent<HiddenRoute>(m_LineQuery, EntityQueryCaptureMode.AtPlayback);
			}
			entityCommandBuffer.AddComponent<HiddenRoute>(entity);
			RequestUpdate();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_UnlockSystem = base.World.GetOrCreateSystemManaged<UnlockSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_PoliciesUISystem = base.World.GetOrCreateSystemManaged<PoliciesUISystem>();
		m_SelectedInfoUISystem = base.World.GetOrCreateSystemManaged<SelectedInfoUISystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UITransportConfigurationData>());
		m_LineQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadWrite<TransportLine>(),
				ComponentType.ReadOnly<RouteWaypoint>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_ModifiedLineQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadWrite<TransportLine>(),
				ComponentType.ReadOnly<RouteWaypoint>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UnlockQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_ColorUpdateArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<ColorUpdated>());
		AddBinding(m_TransportLines = new RawValueBinding("transportationOverview", "lines", BindLines));
		AddBinding(m_PassengerTypes = new RawValueBinding("transportationOverview", "passengerTypes", BindPassengerTypes));
		AddBinding(m_CargoTypes = new RawValueBinding("transportationOverview", "cargoTypes", BindCargoTypes));
		AddBinding(m_SelectedPassengerType = new ValueBinding<string>("transportationOverview", "selectedPassengerType", Enum.GetName(typeof(TransportType), TransportType.Bus)));
		AddBinding(m_SelectedCargoType = new ValueBinding<string>("transportationOverview", "selectedCargoType", "None"));
		AddBinding(new TriggerBinding<Entity>("transportationOverview", "delete", DeleteLine));
		AddBinding(new TriggerBinding<Entity>("transportationOverview", "select", SelectLine));
		AddBinding(new TriggerBinding<Entity, Color32>("transportationOverview", "setColor", SetLineColor));
		AddBinding(new TriggerBinding<Entity, string>("transportationOverview", "rename", SetLineName));
		AddBinding(new TriggerBinding<Entity, bool>("transportationOverview", "setActive", SetLineState));
		AddBinding(new TriggerBinding<Entity, bool>("transportationOverview", "showLine", ShowLine));
		AddBinding(new TriggerBinding<Entity, bool>("transportationOverview", "hideLine", HideLine));
		AddBinding(new TriggerBinding<Entity, int>("transportationOverview", "setSchedule", SetLineSchedule));
		AddBinding(new TriggerBinding("transportationOverview", "resetVisibility", ResetLinesVisibility));
		AddBinding(new TriggerBinding<Entity>("transportationOverview", "toggleHighlight", ToggleHighlight));
		AddBinding(new TriggerBinding<string>("transportationOverview", "setSelectedPassengerType", SetSelectedPassengerType));
		AddBinding(new TriggerBinding<string>("transportationOverview", "setSelectedCargoType", SetSelectedCargoType));
		m_UpdateState = UIUpdateState.Create(base.World, 256);
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		if (base.Enabled)
		{
			m_Config = m_PrefabSystem.GetSingletonPrefab<UITransportConfigurationPrefab>(m_ConfigQuery);
			m_OutOfServicePolicy = m_PrefabSystem.GetEntity(m_Config.m_OutOfServicePolicy);
			m_DayRoutePolicy = m_PrefabSystem.GetEntity(m_Config.m_DayRoutePolicy);
			m_NightRoutePolicy = m_PrefabSystem.GetEntity(m_Config.m_NightRoutePolicy);
			m_CargoTypes.Update();
			m_PassengerTypes.Update();
			m_TransportLines.Update();
			m_SelectedCargoType.Update(GetInitialSelectedType());
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_ModifiedLineQuery.IsEmptyIgnoreFilter || m_UpdateState.Advance())
		{
			m_TransportLines.Update();
		}
		if (PrefabUtils.HasUnlockedPrefab<RouteData>(base.EntityManager, m_UnlockQuery))
		{
			m_CargoTypes.Update();
			m_PassengerTypes.Update();
		}
	}
```

- `public RequestUpdate() : System.Void`  

```csharp
public void RequestUpdate()
	{
		m_UpdateState.ForceUpdate();
	}
```

- `public ResetLinesVisibility() : System.Void`  

```csharp
public void ResetLinesVisibility()
	{
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		entityCommandBuffer.RemoveComponent<HiddenRoute>(m_LineQuery, EntityQueryCaptureMode.AtPlayback);
		entityCommandBuffer.RemoveComponent<Highlighted>(m_LineQuery, EntityQueryCaptureMode.AtPlayback);
		RequestUpdate();
	}
```

- `private SelectLine(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void SelectLine(Entity entity)
	{
		if (base.EntityManager.Exists(entity))
		{
			m_SelectedInfoUISystem.SetSelection(entity);
		}
	}
```

- `private SetLineColor(Unity.Entities.Entity entity, UnityEngine.Color32 color) : System.Void`  

```csharp
private void SetLineColor(Entity entity, Color32 color)
	{
		if (!base.EntityManager.Exists(entity))
		{
			return;
		}
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		entityCommandBuffer.SetComponent(entity, new Game.Routes.Color(color));
		if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<RouteVehicle> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				entityCommandBuffer.AddComponent(buffer[i].m_Vehicle, new Game.Routes.Color(color));
			}
		}
		Entity e = entityCommandBuffer.CreateEntity(m_ColorUpdateArchetype);
		entityCommandBuffer.SetComponent(e, new ColorUpdated(entity));
		RequestUpdate();
	}
```

- `private SetLineName(Unity.Entities.Entity entity, System.String name) : System.Void`  

```csharp
private void SetLineName(Entity entity, string name)
	{
		if (base.EntityManager.Exists(entity))
		{
			m_NameSystem.SetCustomName(entity, name);
			RequestUpdate();
		}
	}
```

- `private SetLineSchedule(Unity.Entities.Entity entity, System.Int32 schedule) : System.Void`  

```csharp
private void SetLineSchedule(Entity entity, int schedule)
	{
		if (base.EntityManager.Exists(entity))
		{
			switch ((RouteSchedule)schedule)
			{
			case RouteSchedule.Day:
				m_PoliciesUISystem.SetPolicy(entity, m_NightRoutePolicy, active: false);
				m_PoliciesUISystem.SetPolicy(entity, m_DayRoutePolicy, active: true);
				break;
			case RouteSchedule.Night:
				m_PoliciesUISystem.SetPolicy(entity, m_NightRoutePolicy, active: true);
				m_PoliciesUISystem.SetPolicy(entity, m_DayRoutePolicy, active: false);
				break;
			default:
				m_PoliciesUISystem.SetPolicy(entity, m_NightRoutePolicy, active: false);
				m_PoliciesUISystem.SetPolicy(entity, m_DayRoutePolicy, active: false);
				break;
			}
			RequestUpdate();
		}
	}
```

- `public SetLineState(Unity.Entities.Entity entity, System.Boolean state) : System.Void`  

```csharp
public void SetLineState(Entity entity, bool state)
	{
		if (base.EntityManager.Exists(entity))
		{
			m_PoliciesUISystem.SetPolicy(entity, m_OutOfServicePolicy, !state);
			RequestUpdate();
		}
	}
```

- `private SetSelectedCargoType(System.String type) : System.Void`  

```csharp
private void SetSelectedCargoType(string type)
	{
		m_SelectedCargoType.Update(type);
	}
```

- `private SetSelectedPassengerType(System.String type) : System.Void`  

```csharp
private void SetSelectedPassengerType(string type)
	{
		m_SelectedPassengerType.Update(type);
	}
```

- `public ShowLine(Unity.Entities.Entity entity, System.Boolean hideOthers) : System.Void`  

```csharp
public void ShowLine(Entity entity, bool hideOthers)
	{
		if (base.EntityManager.Exists(entity))
		{
			EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
			if (hideOthers)
			{
				entityCommandBuffer.AddComponent<HiddenRoute>(m_LineQuery, EntityQueryCaptureMode.AtPlayback);
			}
			entityCommandBuffer.RemoveComponent<HiddenRoute>(entity);
			RequestUpdate();
		}
	}
```

- `public ToggleHighlight(Unity.Entities.Entity entity) : System.Void`  

```csharp
public void ToggleHighlight(Entity entity)
	{
		if (base.EntityManager.Exists(entity))
		{
			EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
			if (!base.EntityManager.HasComponent<Highlighted>(entity))
			{
				entityCommandBuffer.AddComponent<Highlighted>(entity);
			}
			else
			{
				entityCommandBuffer.RemoveComponent<Highlighted>(entity);
			}
		}
	}
```


