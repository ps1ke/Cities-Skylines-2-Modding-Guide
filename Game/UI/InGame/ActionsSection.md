# Game.UI.InGame.ActionsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ActionsSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem;
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
    private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem;
    private Game.Tools.TrafficRoutesSystem m_TrafficRoutesSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_RouteConfigQuery;
    private Game.Prefabs.PolicyPrefab m_RouteOutOfServicePolicy;
    private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy;
    private Game.Prefabs.PolicyPrefab m_EmptyingPolicy;
    private Game.Prefabs.AreaPrefab m_LotPrefab;
    private System.Boolean m_EditingLot;
    private UnityEngine.Color32[] m_TrafficRouteColors;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MovingBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EditingLotBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_TrafficRoutesVisibleBinding;
    private Colossal.UI.Binding.ValueBinding<UnityEngine.Color32[]> m_TrafficRouteColorsBinding;
    private Colossal.UI.Binding.RawValueBinding m_MoveableObjectName;
    private System.Boolean <focusable>k__BackingField;
    private System.Boolean <focusing>k__BackingField;
    private System.Boolean <following>k__BackingField;
    private System.Boolean <followable>k__BackingField;
    private System.Boolean <moveable>k__BackingField;
    private System.Boolean <deletable>k__BackingField;
    private System.Boolean <disabled>k__BackingField;
    private System.Boolean <disableable>k__BackingField;
    private System.Boolean <hasTutorial>k__BackingField;
    private System.Boolean <emptying>k__BackingField;
    private System.Boolean <emptiable>k__BackingField;
    private System.Boolean <hasLotTool>k__BackingField;
    private System.Boolean <hasTrafficRoutes>k__BackingField;

    protected System.String group { protected get; }
    public System.Boolean editingLot { get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private System.Boolean focusable { private get; private set; }
    private System.Boolean focusing { private get; private set; }
    private System.Boolean following { private get; private set; }
    private System.Boolean followable { private get; private set; }
    private System.Boolean moveable { private get; private set; }
    private System.Boolean deletable { private get; private set; }
    private System.Boolean disabled { private get; private set; }
    private System.Boolean disableable { private get; private set; }
    private System.Boolean hasTutorial { private get; private set; }
    private System.Boolean emptying { private get; private set; }
    private System.Boolean emptiable { private get; private set; }
    private System.Boolean hasLotTool { private get; private set; }
    private System.Boolean hasTrafficRoutes { private get; private set; }

    public ActionsSection();

    private System.Void BindObjectName(Colossal.UI.Binding.IJsonWriter binder);
    protected virtual System.Void OnCreate();
    private System.Void OnDelete();
    private System.Void OnFocus();
    private System.Void OnFollow();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnToggle();
    private System.Void OnToggleEmptying();
    private System.Void OnToggleLotTool();
    private System.Void OnToggleMove();
    private System.Void OnToggleTrafficRoutes();
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
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

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem`  

```csharp
private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem;
```

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  

```csharp
private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
```

- `private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem`  

```csharp
private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem;
```

- `private Game.Tools.TrafficRoutesSystem m_TrafficRoutesSystem`  

```csharp
private Game.Tools.TrafficRoutesSystem m_TrafficRoutesSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteConfigQuery;
```

- `private Game.Prefabs.PolicyPrefab m_RouteOutOfServicePolicy`  

```csharp
private Game.Prefabs.PolicyPrefab m_RouteOutOfServicePolicy;
```

- `private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy`  

```csharp
private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy;
```

- `private Game.Prefabs.PolicyPrefab m_EmptyingPolicy`  

```csharp
private Game.Prefabs.PolicyPrefab m_EmptyingPolicy;
```

- `private Game.Prefabs.AreaPrefab m_LotPrefab`  

```csharp
private Game.Prefabs.AreaPrefab m_LotPrefab;
```

- `private System.Boolean m_EditingLot`  

```csharp
private System.Boolean m_EditingLot;
```

- `private UnityEngine.Color32[] m_TrafficRouteColors`  

```csharp
private UnityEngine.Color32[] m_TrafficRouteColors;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MovingBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MovingBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EditingLotBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EditingLotBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_TrafficRoutesVisibleBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_TrafficRoutesVisibleBinding;
```

- `private Colossal.UI.Binding.ValueBinding<UnityEngine.Color32[]> m_TrafficRouteColorsBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<UnityEngine.Color32[]> m_TrafficRouteColorsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_MoveableObjectName`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_MoveableObjectName;
```

- `private System.Boolean <focusable>k__BackingField`  

```csharp
private System.Boolean <focusable>k__BackingField;
```

- `private System.Boolean <focusing>k__BackingField`  

```csharp
private System.Boolean <focusing>k__BackingField;
```

- `private System.Boolean <following>k__BackingField`  

```csharp
private System.Boolean <following>k__BackingField;
```

- `private System.Boolean <followable>k__BackingField`  

```csharp
private System.Boolean <followable>k__BackingField;
```

- `private System.Boolean <moveable>k__BackingField`  

```csharp
private System.Boolean <moveable>k__BackingField;
```

- `private System.Boolean <deletable>k__BackingField`  

```csharp
private System.Boolean <deletable>k__BackingField;
```

- `private System.Boolean <disabled>k__BackingField`  

```csharp
private System.Boolean <disabled>k__BackingField;
```

- `private System.Boolean <disableable>k__BackingField`  

```csharp
private System.Boolean <disableable>k__BackingField;
```

- `private System.Boolean <hasTutorial>k__BackingField`  

```csharp
private System.Boolean <hasTutorial>k__BackingField;
```

- `private System.Boolean <emptying>k__BackingField`  

```csharp
private System.Boolean <emptying>k__BackingField;
```

- `private System.Boolean <emptiable>k__BackingField`  

```csharp
private System.Boolean <emptiable>k__BackingField;
```

- `private System.Boolean <hasLotTool>k__BackingField`  

```csharp
private System.Boolean <hasLotTool>k__BackingField;
```

- `private System.Boolean <hasTrafficRoutes>k__BackingField`  

```csharp
private System.Boolean <hasTrafficRoutes>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `public System.Boolean editingLot { get }`  

```csharp
public System.Boolean editingLot { get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `private System.Boolean focusable { private get; private set }`  

```csharp
private System.Boolean focusable { private get; private set; }
```

- `private System.Boolean focusing { private get; private set }`  

```csharp
private System.Boolean focusing { private get; private set; }
```

- `private System.Boolean following { private get; private set }`  

```csharp
private System.Boolean following { private get; private set; }
```

- `private System.Boolean followable { private get; private set }`  

```csharp
private System.Boolean followable { private get; private set; }
```

- `private System.Boolean moveable { private get; private set }`  

```csharp
private System.Boolean moveable { private get; private set; }
```

- `private System.Boolean deletable { private get; private set }`  

```csharp
private System.Boolean deletable { private get; private set; }
```

- `private System.Boolean disabled { private get; private set }`  

```csharp
private System.Boolean disabled { private get; private set; }
```

- `private System.Boolean disableable { private get; private set }`  

```csharp
private System.Boolean disableable { private get; private set; }
```

- `private System.Boolean hasTutorial { private get; private set }`  

```csharp
private System.Boolean hasTutorial { private get; private set; }
```

- `private System.Boolean emptying { private get; private set }`  

```csharp
private System.Boolean emptying { private get; private set; }
```

- `private System.Boolean emptiable { private get; private set }`  

```csharp
private System.Boolean emptiable { private get; private set; }
```

- `private System.Boolean hasLotTool { private get; private set }`  

```csharp
private System.Boolean hasLotTool { private get; private set; }
```

- `private System.Boolean hasTrafficRoutes { private get; private set }`  

```csharp
private System.Boolean hasTrafficRoutes { private get; private set; }
```


## Constructors

- `public ActionsSection()`  

```csharp
[Preserve]
	public ActionsSection()
	{
	}
```


## Methods

- `private BindObjectName(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindObjectName(IJsonWriter binder)
	{
		if (m_ToolSystem.activeTool == m_ObjectToolSystem && m_ObjectToolSystem.mode == ObjectToolSystem.Mode.Move)
		{
			m_NameSystem.BindName(binder, m_InfoUISystem.selectedEntity);
		}
		else
		{
			binder.WriteNull();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_AreaToolSystem = base.World.GetOrCreateSystemManaged<AreaToolSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_ObjectToolSystem = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
		m_UIInitializeSystem = base.World.GetOrCreateSystemManaged<UIInitializeSystem>();
		m_PoliciesUISystem = base.World.GetOrCreateSystemManaged<PoliciesUISystem>();
		m_LifePathEventSystem = base.World.GetOrCreateSystemManaged<LifePathEventSystem>();
		m_GamePanelUISystem = base.World.GetOrCreateSystemManaged<GamePanelUISystem>();
		m_TrafficRoutesSystem = base.World.GetOrCreateSystemManaged<TrafficRoutesSystem>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_RouteConfigQuery = GetEntityQuery(ComponentType.ReadOnly<RouteConfigurationData>());
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Combine(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
		AddBinding(new TriggerBinding(group, "focus", OnFocus));
		AddBinding(new TriggerBinding(group, "toggleMove", OnToggleMove));
		AddBinding(new TriggerBinding(group, "follow", OnFollow));
		AddBinding(new TriggerBinding(group, "delete", OnDelete));
		AddBinding(new TriggerBinding(group, "toggle", OnToggle));
		AddBinding(new TriggerBinding(group, "toggleEmptying", OnToggleEmptying));
		AddBinding(new TriggerBinding(group, "toggleLotTool", OnToggleLotTool));
		AddBinding(new TriggerBinding(group, "toggleTrafficRoutes", OnToggleTrafficRoutes));
		AddBinding(m_MovingBinding = new ValueBinding<bool>(group, "moving", initialValue: false));
		AddBinding(m_EditingLotBinding = new ValueBinding<bool>(group, "editingLot", initialValue: false));
		AddBinding(m_MoveableObjectName = new RawValueBinding(group, "moveableObjectName", BindObjectName));
		AddBinding(m_TrafficRouteColorsBinding = new ValueBinding<Color32[]>(group, "trafficRouteColors", m_TrafficRouteColors, new ArrayWriter<Color32>()));
		AddBinding(m_TrafficRoutesVisibleBinding = new ValueBinding<bool>(group, "trafficRoutesVisible", m_TrafficRoutesSystem.routesVisible));
	}
```

- `private OnDelete() : System.Void`  

```csharp
private void OnDelete()
	{
		if (base.EntityManager.Exists(selectedEntity))
		{
			if (base.EntityManager.HasComponent<Building>(selectedEntity))
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_BulldozeSound);
			}
			else
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_DeletetEntitySound);
			}
			m_EndFrameBarrier.CreateCommandBuffer().AddComponent<Deleted>(selectedEntity);
		}
	}
```

- `private OnFocus() : System.Void`  

```csharp
private void OnFocus()
	{
		m_InfoUISystem.Focus((!focusing) ? selectedEntity : Entity.Null);
	}
```

- `private OnFollow() : System.Void`  

```csharp
private void OnFollow()
	{
		if (!base.EntityManager.HasComponent<Followed>(selectedEntity))
		{
			m_LifePathEventSystem.FollowCitizen(selectedEntity);
			m_GamePanelUISystem.ShowPanel<LifePathPanel>(selectedEntity);
		}
		else
		{
			m_LifePathEventSystem.UnfollowCitizen(selectedEntity);
		}
		m_InfoUISystem.SetDirty();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		foreach (PolicyPrefab policy in m_UIInitializeSystem.policies)
		{
			switch (policy.name)
			{
			case "Route Out of Service":
				m_RouteOutOfServicePolicy = policy;
				break;
			case "Out of Service":
				m_BuildingOutOfServicePolicy = policy;
				break;
			case "Empty":
				m_EmptyingPolicy = policy;
				break;
			}
		}
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		focusable = !base.EntityManager.HasComponent<BuildingExtensionData>(selectedPrefab) && (!base.EntityManager.HasComponent<Household>(selectedEntity) || base.EntityManager.HasComponent<PropertyRenter>(selectedEntity));
		focusing = SelectedInfoUISystem.s_CameraController != null && SelectedInfoUISystem.s_CameraController.controllerEnabled && SelectedInfoUISystem.s_CameraController.followedEntity == selectedEntity;
		moveable = base.EntityManager.HasComponent<Game.Objects.Object>(selectedEntity) && base.EntityManager.HasComponent<Static>(selectedEntity) && !base.EntityManager.HasComponent<Native>(selectedEntity) && ((!base.EntityManager.HasComponent<Building>(selectedEntity)) ? (!base.EntityManager.HasComponent<Owner>(selectedEntity) && !base.EntityManager.HasComponent<Game.Objects.OutsideConnection>(selectedEntity)) : (!base.EntityManager.HasComponent<Game.Buildings.WaterPowered>(selectedEntity) && (!base.EntityManager.HasComponent<Owner>(selectedEntity) || base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(selectedEntity)) && (!base.EntityManager.HasComponent<SpawnableBuildingData>(selectedPrefab) || base.EntityManager.HasComponent<SignatureBuildingData>(selectedPrefab))));
		followable = base.EntityManager.HasComponent<Citizen>(selectedEntity);
		following = base.EntityManager.HasComponent<Followed>(selectedEntity);
		deletable = base.EntityManager.HasComponent<District>(selectedEntity) || base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(selectedEntity) || (base.EntityManager.HasComponent<TransportLine>(selectedEntity) && base.EntityManager.HasComponent<Route>(selectedEntity));
		disabled = (base.EntityManager.TryGetComponent<Building>(selectedEntity, out var component) && BuildingUtils.CheckOption(component, BuildingOption.Inactive)) || (base.EntityManager.TryGetComponent<Extension>(selectedEntity, out var component2) && (component2.m_Flags & ExtensionFlags.Disabled) != ExtensionFlags.None) || (base.EntityManager.TryGetComponent<Route>(selectedEntity, out var component3) && RouteUtils.CheckOption(component3, RouteOption.Inactive));
		if (base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(selectedEntity))
		{
			disableable = true;
			base.tooltipKeys.Add("Building");
		}
		else if (base.EntityManager.HasComponent<Policy>(selectedEntity))
		{
			if (base.EntityManager.HasComponent<Building>(selectedEntity) && base.EntityManager.HasComponent<CityServiceUpkeep>(selectedEntity) && base.EntityManager.HasComponent<Efficiency>(selectedEntity))
			{
				disableable = true;
				base.tooltipKeys.Add("Building");
			}
			if (base.EntityManager.HasComponent<Route>(selectedEntity) && base.EntityManager.HasComponent<TransportLine>(selectedEntity) && base.EntityManager.HasComponent<RouteWaypoint>(selectedEntity))
			{
				disableable = true;
			}
		}
		emptying = base.EntityManager.TryGetComponent<Building>(selectedEntity, out component) && BuildingUtils.CheckOption(component, BuildingOption.Empty);
		emptiable = base.EntityManager.HasComponent<Policy>(selectedEntity) && base.EntityManager.HasComponent<Building>(selectedEntity) && base.EntityManager.TryGetComponent<GarbageFacilityData>(selectedPrefab, out var component4) && component4.m_LongTermStorage;
		if (base.EntityManager.TryGetBuffer(selectedPrefab, isReadOnly: true, out DynamicBuffer<Game.Prefabs.SubArea> buffer) && buffer.Length > 0)
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				AreaPrefab prefab = m_PrefabSystem.GetPrefab<AreaPrefab>(buffer[i].m_Prefab);
				if (prefab != null && prefab.Has<LotPrefab>())
				{
					m_LotPrefab = prefab;
					hasLotTool = ((LotPrefab)prefab).m_AllowEditing;
					break;
				}
			}
		}
		if (!hasLotTool && base.EntityManager.HasComponent<SpawnableBuildingData>(selectedPrefab) && base.EntityManager.TryGetComponent<Attached>(selectedEntity, out var component5) && base.EntityManager.TryGetBuffer(component5.m_Parent, isReadOnly: true, out DynamicBuffer<Game.Areas.SubArea> buffer2) && buffer2.Length > 0)
		{
			for (int j = 0; j < buffer2.Length; j++)
			{
				if (base.EntityManager.HasComponent<Game.Areas.Lot>(buffer2[j].m_Area) && base.EntityManager.TryGetComponent<PrefabRef>(buffer2[j].m_Area, out var component6))
				{
					AreaPrefab prefab2 = m_PrefabSystem.GetPrefab<AreaPrefab>(component6.m_Prefab);
					if (prefab2 != null)
					{
						m_LotPrefab = prefab2;
						hasLotTool = true;
						break;
					}
				}
			}
		}
		if (m_TrafficRouteColors == null)
		{
			RouteConfigurationData singleton = m_RouteConfigQuery.GetSingleton<RouteConfigurationData>();
			m_TrafficRouteColors = new Color32[5]
			{
				m_PrefabSystem.GetPrefab<LivePathPrefab>(singleton.m_CarPathVisualization).color,
				m_PrefabSystem.GetPrefab<LivePathPrefab>(singleton.m_WatercraftPathVisualization).color,
				m_PrefabSystem.GetPrefab<LivePathPrefab>(singleton.m_AircraftPathVisualization).color,
				m_PrefabSystem.GetPrefab<LivePathPrefab>(singleton.m_TrainPathVisualization).color,
				m_PrefabSystem.GetPrefab<LivePathPrefab>(singleton.m_HumanPathVisualization).color
			};
			m_TrafficRouteColorsBinding.Update(m_TrafficRouteColors);
		}
		hasTrafficRoutes = base.EntityManager.HasComponent<Building>(selectedEntity) || base.EntityManager.HasComponent<Aggregate>(selectedEntity) || base.EntityManager.HasComponent<Game.Net.Node>(selectedEntity) || base.EntityManager.HasComponent<Edge>(selectedEntity) || base.EntityManager.HasComponent<Game.Routes.TransportStop>(selectedEntity) || base.EntityManager.HasComponent<Game.Objects.OutsideConnection>(selectedEntity) || base.EntityManager.HasComponent<Human>(selectedEntity) || base.EntityManager.HasComponent<Vehicle>(selectedEntity) || base.EntityManager.HasComponent<Citizen>(selectedEntity) || base.EntityManager.HasComponent<Household>(selectedEntity);
		m_TrafficRoutesVisibleBinding.Update(m_TrafficRoutesSystem.routesVisible);
	}
```

- `private OnToggle() : System.Void`  

```csharp
private void OnToggle()
	{
		if (base.EntityManager.HasComponent<Route>(selectedEntity) && base.EntityManager.HasComponent<TransportLine>(selectedEntity) && base.EntityManager.HasComponent<RouteWaypoint>(selectedEntity))
		{
			m_PoliciesUISystem.SetSelectedInfoPolicy(m_PrefabSystem.GetEntity(m_RouteOutOfServicePolicy), !disabled);
		}
		else if ((base.EntityManager.HasComponent<Building>(selectedEntity) && base.EntityManager.HasComponent<Policy>(selectedEntity) && base.EntityManager.HasComponent<CityServiceUpkeep>(selectedEntity) && base.EntityManager.HasComponent<Efficiency>(selectedEntity)) || base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(selectedEntity))
		{
			m_PoliciesUISystem.SetSelectedInfoPolicy(m_PrefabSystem.GetEntity(m_BuildingOutOfServicePolicy), !disabled);
		}
	}
```

- `private OnToggleEmptying() : System.Void`  

```csharp
private void OnToggleEmptying()
	{
		m_PoliciesUISystem.SetSelectedInfoPolicy(m_PrefabSystem.GetEntity(m_EmptyingPolicy), !emptying);
	}
```

- `private OnToggleLotTool() : System.Void`  

```csharp
private void OnToggleLotTool()
	{
		if (m_EditingLot)
		{
			m_ToolSystem.activeTool = m_DefaultToolSystem;
		}
		else if (m_LotPrefab != null)
		{
			m_EditingLot = true;
			m_AreaToolSystem.prefab = m_LotPrefab;
			m_ToolSystem.activeTool = m_AreaToolSystem;
		}
	}
```

- `private OnToggleMove() : System.Void`  

```csharp
private void OnToggleMove()
	{
		if (moveable)
		{
			if (m_ToolSystem.activeTool == m_ObjectToolSystem)
			{
				m_ToolSystem.activeTool = m_DefaultToolSystem;
				return;
			}
			m_ObjectToolSystem.StartMoving(selectedEntity);
			m_ToolSystem.activeTool = m_ObjectToolSystem;
		}
	}
```

- `private OnToggleTrafficRoutes() : System.Void`  

```csharp
private void OnToggleTrafficRoutes()
	{
		m_TrafficRoutesSystem.routesVisible = !m_TrafficRoutesSystem.routesVisible;
		m_InfoUISystem.SetDirty();
	}
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private void OnToolChanged(ToolBaseSystem tool)
	{
		if (tool != m_AreaToolSystem)
		{
			m_EditingLot = false;
		}
		m_MoveableObjectName.Update();
		m_MovingBinding.Update(tool == m_ObjectToolSystem && m_ObjectToolSystem.mode == ObjectToolSystem.Mode.Move);
		m_EditingLotBinding.Update(tool == m_AreaToolSystem && hasLotTool && m_EditingLot);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = selectedEntity != Entity.Null;
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("focusable");
		writer.Write(focusable);
		writer.PropertyName("focusing");
		writer.Write(focusing);
		writer.PropertyName("following");
		writer.Write(following);
		writer.PropertyName("followable");
		writer.Write(followable);
		writer.PropertyName("moveable");
		writer.Write(moveable);
		writer.PropertyName("deletable");
		writer.Write(deletable);
		writer.PropertyName("disabled");
		writer.Write(disabled);
		writer.PropertyName("disableable");
		writer.Write(disableable);
		writer.PropertyName("emptying");
		writer.Write(emptying);
		writer.PropertyName("emptiable");
		writer.Write(emptiable);
		writer.PropertyName("hasLotTool");
		writer.Write(hasLotTool);
		writer.PropertyName("hasTrafficRoutes");
		writer.Write(hasTrafficRoutes);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		focusable = false;
		focusing = false;
		following = false;
		followable = false;
		moveable = false;
		deletable = false;
		disabled = false;
		disableable = false;
		hasTutorial = false;
		emptying = false;
		emptiable = false;
		hasLotTool = false;
		hasTrafficRoutes = false;
		m_LotPrefab = null;
	}
```


