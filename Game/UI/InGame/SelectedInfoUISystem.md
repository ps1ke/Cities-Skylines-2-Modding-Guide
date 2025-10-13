# Game.UI.InGame.SelectedInfoUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SelectedInfoUISystem : Game.UI.UISystemBase
{
    private System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Unity.Mathematics.float3> <eventSelectionChanged>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.TooltipTags> <tooltipTags>k__BackingField;
    private Unity.Mathematics.float3 m_SelectedPosition;
    private Unity.Entities.Entity m_SelectedEntity;
    private Unity.Entities.Entity m_SelectedPrefab;
    private Unity.Entities.Entity m_SelectedRoute;
    private Unity.Entities.Entity m_LastSelectedEntity;
    private Unity.Entities.EntityQuery m_TransportConfigQuery;
    private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_TopSections;
    private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_MiddleSections;
    private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_BottomSections;
    private Game.UI.InGame.TitleSection m_TitleSection;
    private Game.UI.InGame.DeveloperSection m_DeveloperSection;
    private Game.UI.InGame.LineVisualizerSection m_LineVisualizerSection;
    private Game.UI.InGame.HouseholdSidebarSection m_HouseholdSidebarSection;
    private Game.UI.Debug.DebugUISystem m_DebugUISystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedEntityBinding;
    private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedTrailerControllerBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedUITagBinding;
    private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_SelectedRouteBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveSelectionBinding;
    private Colossal.UI.Binding.RawValueBinding m_TopSectionsBinding;
    private Colossal.UI.Binding.RawValueBinding m_MiddleSectionsBinding;
    private Colossal.UI.Binding.RawValueBinding m_BottomSectionsBinding;
    private Colossal.UI.Binding.RawValueBinding m_IDSectionBinding;
    private Colossal.UI.Binding.RawValueBinding m_LineVisualizerSectionBinding;
    private Colossal.UI.Binding.RawValueBinding m_DeveloperSectionBinding;
    private Colossal.UI.Binding.RawValueBinding m_HouseholdSidebarSectionBinding;
    private Colossal.UI.Binding.ValueBinding<Unity.Mathematics.float2> m_PositionBinding;
    private Colossal.UI.Binding.RawValueBinding m_TooltipTagsBinding;
    private System.Boolean m_BindingsDirty;
    private Game.UI.UIUpdateState m_UpdateState;
    public static Game.OrbitCameraController s_CameraController;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public Unity.Mathematics.float3 selectedPosition { get; }
    public Unity.Entities.Entity selectedEntity { get; }
    public Unity.Entities.Entity selectedPrefab { get; }
    public Unity.Entities.Entity selectedRoute { get; set; }
    public System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Unity.Mathematics.float3> eventSelectionChanged { get; set; }
    public System.Collections.Generic.List<Game.UI.InGame.TooltipTags> tooltipTags { get; set; }

    public SelectedInfoUISystem();

    private Unity.Entities.Entity <OnCreate>b__54_0();
    private System.Void <OnCreate>b__54_1(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void <OnCreate>b__54_2(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void <OnCreate>b__54_3(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void <OnCreate>b__54_4(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void <OnCreate>b__54_5(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void <OnCreate>b__54_6(Colossal.UI.Binding.IJsonWriter writer);
    public System.Void AddBottomSection(Game.UI.InGame.ISectionSource section);
    public System.Void AddDeveloperInfo(Game.UI.InGame.ISubsectionSource subsection);
    public System.Void AddMiddleSection(Game.UI.InGame.ISectionSource section);
    private System.Void AddSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> topSections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> sections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> bottomSections);
    public System.Void AddTopSection(Game.UI.InGame.ISectionSource section);
    private static System.Void FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.EntityManager entityManager);
    private static System.Void FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.Entity location, Unity.Entities.EntityManager entityManager);
    private System.Void FilterSelection(Unity.Entities.Entity& entity, Unity.Entities.Entity& prefab);
    public System.Void Focus(Unity.Entities.Entity entity);
    private static Unity.Mathematics.float3 GetAggregatePosition(Unity.Entities.DynamicBuffer<Game.Net.LabelPosition> labelPositions, System.Int32& selectedIndex);
    private static Unity.Mathematics.float3 GetCurvePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Curve curve, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation);
    private static Game.Objects.Transform GetInterpolatedPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Objects.TransformFrame> transformFrames, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds);
    private static Unity.Mathematics.float3 GetNodePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Node node, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation);
    private static Game.Objects.Transform GetObjectPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Transform transform, Colossal.Mathematics.Bounds3& bounds);
    private static Game.Objects.Transform GetRelativePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Relative relative, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds);
    private static Unity.Mathematics.float3 GetRoutePosition(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> routeWaypoints);
    private static System.Boolean IsNearCamera(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager);
    private System.Void OnCameraStoppedFollowing();
    private System.Void OnClearSelection();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnSelect(Unity.Entities.Entity entity);
    private System.Void OnSetSelectedRoute(Unity.Entities.Entity entity);
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem obj);
    protected virtual System.Void OnUpdate();
    private System.Void RefreshSelection();
    public System.Void RequestUpdate();
    private System.Void ResetRouteVisibility();
    private System.Void SetBindingsDirty();
    public System.Void SetDirty();
    public System.Void SetRoutesVisible();
    public System.Void SetSelection(Unity.Entities.Entity entity);
    private System.Void StartFollowing(Unity.Entities.Entity entity);
    private System.Void StopFollowing();
    public static System.Boolean TryGetPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, System.Int32& elementIndex, Unity.Entities.Entity& location, Unity.Mathematics.float3& position, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation, System.Boolean reinterpolate);
    private System.Boolean TryGetSelection(Unity.Entities.Entity& entity);
    private System.Boolean TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config);
    private System.Void UpdatePosition();
    private System.Void UpdateSectionBindings();
    private System.Void UpdateSections();
    private System.Void WriteDeveloperSection(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void WriteSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> list, Colossal.UI.Binding.IJsonWriter binder);
    private System.Void WriteTooltipFlags(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Unity.Mathematics.float3> <eventSelectionChanged>k__BackingField`  

```csharp
private System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Unity.Mathematics.float3> <eventSelectionChanged>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.TooltipTags> <tooltipTags>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.TooltipTags> <tooltipTags>k__BackingField;
```

- `private Unity.Mathematics.float3 m_SelectedPosition`  

```csharp
private Unity.Mathematics.float3 m_SelectedPosition;
```

- `private Unity.Entities.Entity m_SelectedEntity`  

```csharp
private Unity.Entities.Entity m_SelectedEntity;
```

- `private Unity.Entities.Entity m_SelectedPrefab`  

```csharp
private Unity.Entities.Entity m_SelectedPrefab;
```

- `private Unity.Entities.Entity m_SelectedRoute`  

```csharp
private Unity.Entities.Entity m_SelectedRoute;
```

- `private Unity.Entities.Entity m_LastSelectedEntity`  

```csharp
private Unity.Entities.Entity m_LastSelectedEntity;
```

- `private Unity.Entities.EntityQuery m_TransportConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportConfigQuery;
```

- `private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_TopSections`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_TopSections;
```

- `private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_MiddleSections`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_MiddleSections;
```

- `private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_BottomSections`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_BottomSections;
```

- `private Game.UI.InGame.TitleSection m_TitleSection`  

```csharp
private Game.UI.InGame.TitleSection m_TitleSection;
```

- `private Game.UI.InGame.DeveloperSection m_DeveloperSection`  

```csharp
private Game.UI.InGame.DeveloperSection m_DeveloperSection;
```

- `private Game.UI.InGame.LineVisualizerSection m_LineVisualizerSection`  

```csharp
private Game.UI.InGame.LineVisualizerSection m_LineVisualizerSection;
```

- `private Game.UI.InGame.HouseholdSidebarSection m_HouseholdSidebarSection`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection m_HouseholdSidebarSection;
```

- `private Game.UI.Debug.DebugUISystem m_DebugUISystem`  

```csharp
private Game.UI.Debug.DebugUISystem m_DebugUISystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedEntityBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedEntityBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedTrailerControllerBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedTrailerControllerBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedUITagBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedUITagBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_SelectedRouteBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_SelectedRouteBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveSelectionBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveSelectionBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopSectionsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopSectionsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_MiddleSectionsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_MiddleSectionsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_BottomSectionsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_BottomSectionsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_IDSectionBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_IDSectionBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_LineVisualizerSectionBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_LineVisualizerSectionBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_DeveloperSectionBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_DeveloperSectionBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_HouseholdSidebarSectionBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_HouseholdSidebarSectionBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Mathematics.float2> m_PositionBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Mathematics.float2> m_PositionBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_TooltipTagsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TooltipTagsBinding;
```

- `private System.Boolean m_BindingsDirty`  

```csharp
private System.Boolean m_BindingsDirty;
```

- `private Game.UI.UIUpdateState m_UpdateState`  

```csharp
private Game.UI.UIUpdateState m_UpdateState;
```

- `public static Game.OrbitCameraController s_CameraController`  

```csharp
public static Game.OrbitCameraController s_CameraController;
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

- `public Unity.Mathematics.float3 selectedPosition { get }`  

```csharp
public Unity.Mathematics.float3 selectedPosition { get; }
```

- `public Unity.Entities.Entity selectedEntity { get }`  

```csharp
public Unity.Entities.Entity selectedEntity { get; }
```

- `public Unity.Entities.Entity selectedPrefab { get }`  

```csharp
public Unity.Entities.Entity selectedPrefab { get; }
```

- `public Unity.Entities.Entity selectedRoute { get; set }`  

```csharp
public Unity.Entities.Entity selectedRoute { get; set; }
```

- `public System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Unity.Mathematics.float3> eventSelectionChanged { get; set }`  

```csharp
public System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Unity.Mathematics.float3> eventSelectionChanged { get; set; }
```

- `public System.Collections.Generic.List<Game.UI.InGame.TooltipTags> tooltipTags { get; set }`  

```csharp
public System.Collections.Generic.List<Game.UI.InGame.TooltipTags> tooltipTags { get; set; }
```


## Constructors

- `public SelectedInfoUISystem()`  

```csharp
[Preserve]
	public SelectedInfoUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__54_0() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__54_0();
```

- `private <OnCreate>b__54_1(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__54_1(Colossal.UI.Binding.IJsonWriter writer);
```

- `private <OnCreate>b__54_2(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__54_2(Colossal.UI.Binding.IJsonWriter writer);
```

- `private <OnCreate>b__54_3(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__54_3(Colossal.UI.Binding.IJsonWriter writer);
```

- `private <OnCreate>b__54_4(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__54_4(Colossal.UI.Binding.IJsonWriter writer);
```

- `private <OnCreate>b__54_5(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__54_5(Colossal.UI.Binding.IJsonWriter writer);
```

- `private <OnCreate>b__54_6(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__54_6(Colossal.UI.Binding.IJsonWriter writer);
```

- `public AddBottomSection(Game.UI.InGame.ISectionSource section) : System.Void`  

```csharp
public void AddBottomSection(ISectionSource section)
	{
		m_BottomSections.Add(section);
	}
```

- `public AddDeveloperInfo(Game.UI.InGame.ISubsectionSource subsection) : System.Void`  

```csharp
public void AddDeveloperInfo(ISubsectionSource subsection)
	{
		m_DeveloperSection.AddSubsection(subsection);
	}
```

- `public AddMiddleSection(Game.UI.InGame.ISectionSource section) : System.Void`  

```csharp
public void AddMiddleSection(ISectionSource section)
	{
		m_MiddleSections.Add(section);
	}
```

- `private AddSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> topSections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> sections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> bottomSections) : System.Void`  

```csharp
private void AddSections(List<ISectionSource> topSections, List<ISectionSource> sections, List<ISectionSource> bottomSections)
	{
		m_TitleSection = base.World.GetOrCreateSystemManaged<TitleSection>();
		m_LineVisualizerSection = base.World.GetOrCreateSystemManaged<LineVisualizerSection>();
		m_HouseholdSidebarSection = base.World.GetOrCreateSystemManaged<HouseholdSidebarSection>();
		m_DeveloperSection = base.World.GetOrCreateSystemManaged<DeveloperSection>();
		topSections.Add(base.World.GetOrCreateSystemManaged<NotificationsSection>());
		topSections.Add(base.World.GetOrCreateSystemManaged<AverageHappinessSection>());
		topSections.Add(base.World.GetOrCreateSystemManaged<StatusSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DescriptionSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ContentPrerequisiteSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DestroyedBuildingSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DestroyedTreeSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PoliciesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<LevelSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<UpkeepSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<UpgradePropertiesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<EfficiencySection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ResidentsSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<EmployeesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<AttractivenessSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ComfortSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<EducationSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ElectricitySection>());
		sections.Add(base.World.GetOrCreateSystemManaged<BatterySection>());
		sections.Add(base.World.GetOrCreateSystemManaged<TransformerSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<HealthcareSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DeathcareSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<GarbageSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PoliceSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ShelterSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PrisonSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<SewageSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<WaterSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ParkSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ParkingSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<MailSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<CitizenSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DummyHumanSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<AnimalSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PrivateVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PublicTransportVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<CargoTransportVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DeliveryVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<HealthcareVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DeathcareVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<FireVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PoliceVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<GarbageVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PostVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<MaintenanceVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ExtractorVehicleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DistrictsSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<LocalServicesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PassengersSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<CargoSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<LoadSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<CompanySection>());
		sections.Add(base.World.GetOrCreateSystemManaged<StorageSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<TradedResourcesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<SelectVehiclesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<LineSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<TicketPriceSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<VehicleCountSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ScheduleSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ColorSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<LinesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<ResourceSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<RoadSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<PollutionSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<DispatchedVehiclesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<VehiclesSection>());
		sections.Add(base.World.GetOrCreateSystemManaged<UpgradesSection>());
		bottomSections.Add(base.World.GetOrCreateSystemManaged<ActionsSection>());
	}
```

- `public AddTopSection(Game.UI.InGame.ISectionSource section) : System.Void`  

```csharp
public void AddTopSection(ISectionSource section)
	{
		m_TopSections.Add(section);
	}
```

- `private static FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.EntityManager entityManager) : System.Void`  

```csharp
private static void FilterPositionTarget(out Entity entity, Entity location, EntityManager entityManager)
	{
		entity = Entity.Null;
		if (entityManager.HasComponent<Game.Objects.Object>(location))
		{
			entity = location;
		}
		Owner component;
		while (entityManager.TryGetComponent<Owner>(location, out component))
		{
			location = component.m_Owner;
			if (entityManager.HasComponent<Game.Objects.Object>(location))
			{
				entity = location;
			}
		}
		if (!entityManager.HasComponent<Game.Net.OutsideConnection>(location) || !entityManager.TryGetBuffer(location, isReadOnly: true, out DynamicBuffer<Game.Objects.SubObject> buffer))
		{
			return;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity subObject = buffer[i].m_SubObject;
			if (entityManager.HasComponent<Game.Objects.OutsideConnection>(subObject))
			{
				entity = subObject;
			}
		}
	}
```

- `private static FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.Entity location, Unity.Entities.EntityManager entityManager) : System.Void`  

```csharp
private static void FilterPositionTarget(out Entity entity, Entity location, EntityManager entityManager)
	{
		entity = Entity.Null;
		if (entityManager.HasComponent<Game.Objects.Object>(location))
		{
			entity = location;
		}
		Owner component;
		while (entityManager.TryGetComponent<Owner>(location, out component))
		{
			location = component.m_Owner;
			if (entityManager.HasComponent<Game.Objects.Object>(location))
			{
				entity = location;
			}
		}
		if (!entityManager.HasComponent<Game.Net.OutsideConnection>(location) || !entityManager.TryGetBuffer(location, isReadOnly: true, out DynamicBuffer<Game.Objects.SubObject> buffer))
		{
			return;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity subObject = buffer[i].m_SubObject;
			if (entityManager.HasComponent<Game.Objects.OutsideConnection>(subObject))
			{
				entity = subObject;
			}
		}
	}
```

- `private FilterSelection(Unity.Entities.Entity& entity, Unity.Entities.Entity& prefab) : System.Void`  

```csharp
private void FilterSelection(ref Entity entity, ref Entity prefab)
	{
		if (base.EntityManager.HasComponent<Icon>(entity) && base.EntityManager.TryGetComponent<Owner>(entity, out var component))
		{
			CurrentBuilding component3;
			if (base.EntityManager.HasComponent<RouteLane>(component.m_Owner) && base.EntityManager.HasComponent<Waypoint>(component.m_Owner) && base.EntityManager.TryGetComponent<Owner>(component.m_Owner, out var component2))
			{
				entity = component2.m_Owner;
			}
			else if (base.EntityManager.TryGetComponent<CurrentBuilding>(component.m_Owner, out component3))
			{
				if (base.EntityManager.Exists(component3.m_CurrentBuilding))
				{
					entity = component3.m_CurrentBuilding;
				}
			}
			else
			{
				entity = component.m_Owner;
			}
			if (base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component4))
			{
				prefab = component4.m_Prefab;
			}
			SetSelection(entity);
		}
		if (base.EntityManager.TryGetComponent<Game.Creatures.Resident>(entity, out var component5) && base.EntityManager.TryGetComponent<PrefabRef>(component5.m_Citizen, out var component6))
		{
			entity = component5.m_Citizen;
			prefab = component6.m_Prefab;
		}
		if (base.EntityManager.TryGetComponent<Game.Creatures.Pet>(entity, out var component7) && base.EntityManager.TryGetComponent<PrefabRef>(component7.m_HouseholdPet, out var component8))
		{
			entity = component7.m_HouseholdPet;
			prefab = component8.m_Prefab;
		}
	}
```

- `public Focus(Unity.Entities.Entity entity) : System.Void`  

```csharp
public void Focus(Entity entity)
	{
		if (entity == Entity.Null)
		{
			StopFollowing();
		}
		else
		{
			StartFollowing(entity);
		}
	}
```

- `private static GetAggregatePosition(Unity.Entities.DynamicBuffer<Game.Net.LabelPosition> labelPositions, System.Int32& selectedIndex) : Unity.Mathematics.float3`  

```csharp
private static float3 GetAggregatePosition(DynamicBuffer<LabelPosition> labelPositions, ref int selectedIndex)
	{
		float3 result = default(float3);
		float3 y = ((s_CameraController != null) ? s_CameraController.pivot : default(Vector3));
		float num = float.MaxValue;
		int num2 = -1;
		for (int i = 0; i < labelPositions.Length; i++)
		{
			LabelPosition labelPosition = labelPositions[i];
			float3 @float = MathUtils.Position(labelPosition.m_Curve, 0.5f);
			float num3 = math.distancesq(@float, y);
			if (labelPosition.m_ElementIndex == selectedIndex)
			{
				return @float;
			}
			if (!(num3 >= num))
			{
				result = @float;
				num = num3;
				num2 = labelPosition.m_ElementIndex;
			}
		}
		selectedIndex = num2;
		return result;
	}
```

- `private static GetCurvePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Curve curve, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation) : Unity.Mathematics.float3`  

```csharp
private static float3 GetCurvePosition(Entity entity, EntityManager entityManager, Curve curve, out Bounds3 bounds, out quaternion rotation)
	{
		float3 @float = MathUtils.Position(curve.m_Bezier, 0.5f);
		bounds = new Bounds3(@float, @float);
		rotation = quaternion.Euler(MathUtils.Tangent(curve.m_Bezier, 0.5f));
		if (entityManager.TryGetComponent<PrefabRef>(entity, out var component) && entityManager.TryGetComponent<NetGeometryData>(component.m_Prefab, out var component2))
		{
			bounds.y = @float.y + component2.m_DefaultSurfaceHeight;
		}
		return @float;
	}
```

- `private static GetInterpolatedPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Objects.TransformFrame> transformFrames, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  

```csharp
private static Game.Objects.Transform GetInterpolatedPosition(Entity entity, EntityManager entityManager, DynamicBuffer<TransformFrame> transformFrames, bool reinterpolate, out Bounds3 bounds)
	{
		InterpolatedTransform interpolatedTransform;
		if (!reinterpolate && IsNearCamera(entity, entityManager))
		{
			interpolatedTransform = entityManager.GetComponentData<InterpolatedTransform>(entity);
		}
		else
		{
			RenderingSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<RenderingSystem>();
			UpdateFrame sharedComponent = entityManager.GetSharedComponent<UpdateFrame>(entity);
			ObjectInterpolateSystem.CalculateUpdateFrames(orCreateSystemManaged.frameIndex, orCreateSystemManaged.frameTime, sharedComponent.m_Index, out var updateFrame, out var updateFrame2, out var framePosition);
			TransformFrame frame = transformFrames[(int)updateFrame];
			TransformFrame frame2 = transformFrames[(int)updateFrame2];
			interpolatedTransform = ObjectInterpolateSystem.CalculateTransform(frame, frame2, framePosition);
		}
		return GetObjectPosition(entity, entityManager, interpolatedTransform.ToTransform(), out bounds);
	}
```

- `private static GetNodePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Node node, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation) : Unity.Mathematics.float3`  

```csharp
private static float3 GetNodePosition(Entity entity, EntityManager entityManager, Game.Net.Node node, out Bounds3 bounds, out quaternion rotation)
	{
		bounds = new Bounds3(node.m_Position, node.m_Position);
		if (entityManager.TryGetComponent<PrefabRef>(entity, out var component) && entityManager.TryGetComponent<NetGeometryData>(component.m_Prefab, out var component2))
		{
			bounds.y = node.m_Position.y + component2.m_DefaultSurfaceHeight;
		}
		rotation = node.m_Rotation;
		return node.m_Position;
	}
```

- `private static GetObjectPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Transform transform, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  

```csharp
private static Game.Objects.Transform GetObjectPosition(Entity entity, EntityManager entityManager, Game.Objects.Transform transform, out Bounds3 bounds)
	{
		bounds = new Bounds3(transform.m_Position, transform.m_Position);
		if (entityManager.TryGetComponent<PrefabRef>(entity, out var component) && entityManager.TryGetComponent<ObjectGeometryData>(component.m_Prefab, out var component2))
		{
			bounds = ObjectUtils.CalculateBounds(transform.m_Position, transform.m_Rotation, component2);
		}
		return transform;
	}
```

- `private static GetRelativePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Relative relative, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  

```csharp
private static Game.Objects.Transform GetRelativePosition(Entity entity, EntityManager entityManager, Relative relative, bool reinterpolate, out Bounds3 bounds)
	{
		Game.Objects.Transform transform = entityManager.GetComponentData<Game.Objects.Transform>(entity);
		Entity entity2 = Entity.Null;
		Owner component2;
		if (entityManager.TryGetComponent<CurrentVehicle>(entity, out var component))
		{
			entity2 = component.m_Vehicle;
		}
		else if (entityManager.TryGetComponent<Owner>(entity, out component2))
		{
			entity2 = component2.m_Owner;
		}
		Game.Objects.Transform interpolatedPosition;
		if (entityManager.TryGetBuffer(entity2, isReadOnly: true, out DynamicBuffer<TransformFrame> buffer))
		{
			interpolatedPosition = GetInterpolatedPosition(entity2, entityManager, buffer, reinterpolate, out var _);
			transform = ObjectUtils.LocalToWorld(interpolatedPosition, relative.ToTransform());
		}
		else if (entityManager.TryGetComponent<Game.Objects.Transform>(entity2, out interpolatedPosition))
		{
			transform = ObjectUtils.LocalToWorld(interpolatedPosition, relative.ToTransform());
		}
		return GetObjectPosition(entity, entityManager, transform, out bounds);
	}
```

- `private static GetRoutePosition(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> routeWaypoints) : Unity.Mathematics.float3`  

```csharp
private static float3 GetRoutePosition(EntityManager entityManager, DynamicBuffer<RouteWaypoint> routeWaypoints)
	{
		float3 result = default(float3);
		float3 y = ((s_CameraController != null) ? s_CameraController.pivot : default(Vector3));
		float num = float.MaxValue;
		for (int i = 0; i < routeWaypoints.Length; i++)
		{
			if (entityManager.TryGetComponent<Position>(routeWaypoints[i].m_Waypoint, out var component))
			{
				float num2 = math.distancesq(component.m_Position, y);
				if (!(num2 >= num))
				{
					result = component.m_Position;
					num = num2;
				}
			}
		}
		return result;
	}
```

- `private static IsNearCamera(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager) : System.Boolean`  

```csharp
private static bool IsNearCamera(Entity entity, EntityManager entityManager)
	{
		if (entityManager.TryGetComponent<CullingInfo>(entity, out var component) && component.m_CullingIndex != 0)
		{
			JobHandle dependencies;
			NativeList<PreCullingData> cullingData = entityManager.World.GetOrCreateSystemManaged<PreCullingSystem>().GetCullingData(readOnly: true, out dependencies);
			dependencies.Complete();
			return (cullingData[component.m_CullingIndex].m_Flags & PreCullingFlags.NearCamera) != 0;
		}
		return false;
	}
```

- `private OnCameraStoppedFollowing() : System.Void`  

```csharp
private void OnCameraStoppedFollowing()
	{
		StopFollowing();
	}
```

- `private OnClearSelection() : System.Void`  

```csharp
private void OnClearSelection()
	{
		SetSelection(Entity.Null);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		AddSections(m_TopSections = new List<ISectionSource>(), m_MiddleSections = new List<ISectionSource>(), m_BottomSections = new List<ISectionSource>());
		tooltipTags = new List<TooltipTags>();
		m_DebugUISystem = base.World.GetOrCreateSystemManaged<DebugUISystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_TransportConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UITransportConfigurationData>());
		m_SelectedEntity = Entity.Null;
		m_SelectedPrefab = Entity.Null;
		m_LastSelectedEntity = Entity.Null;
		AddBinding(m_SelectedEntityBinding = new ValueBinding<Entity>("selectedInfo", "selectedEntity", Entity.Null));
		AddBinding(m_SelectedTrailerControllerBinding = new ValueBinding<Entity>("selectedInfo", "selectedTrailerController", Entity.Null));
		AddBinding(m_SelectedUITagBinding = new ValueBinding<string>("selectedInfo", "selectedUITag", string.Empty));
		AddBinding(m_SelectedRouteBinding = new GetterValueBinding<Entity>("selectedInfo", "selectedRoute", () => m_SelectedRoute));
		AddBinding(m_ActiveSelectionBinding = new ValueBinding<bool>("selectedInfo", "activeSelection", initialValue: false));
		AddBinding(m_TopSectionsBinding = new RawValueBinding("selectedInfo", "topSections", delegate(IJsonWriter writer)
		{
			WriteSections(m_TopSections, writer);
		}));
		AddBinding(m_MiddleSectionsBinding = new RawValueBinding("selectedInfo", "middleSections", delegate(IJsonWriter writer)
		{
			WriteSections(m_MiddleSections, writer);
		}));
		AddBinding(m_BottomSectionsBinding = new RawValueBinding("selectedInfo", "bottomSections", delegate(IJsonWriter writer)
		{
			WriteSections(m_BottomSections, writer);
		}));
		AddBinding(m_IDSectionBinding = new RawValueBinding("selectedInfo", "titleSection", delegate(IJsonWriter writer)
		{
			m_TitleSection.Write(writer);
		}));
		AddBinding(m_LineVisualizerSectionBinding = new RawValueBinding("selectedInfo", "lineVisualizerSection", delegate(IJsonWriter writer)
		{
			m_LineVisualizerSection.Write(writer);
		}));
		AddBinding(m_DeveloperSectionBinding = new RawValueBinding("selectedInfo", "developerSection", WriteDeveloperSection));
		AddBinding(m_HouseholdSidebarSectionBinding = new RawValueBinding("selectedInfo", "householdSidebarSection", delegate(IJsonWriter writer)
		{
			m_HouseholdSidebarSection.Write(writer);
		}));
		AddBinding(m_PositionBinding = new ValueBinding<float2>("selectedInfo", "position", default(float2)));
		AddBinding(m_TooltipTagsBinding = new RawValueBinding("selectedInfo", "tooltipTags", WriteTooltipFlags));
		AddBinding(new TriggerBinding<Entity>("selectedInfo", "selectEntity", OnSelect));
		AddBinding(new TriggerBinding("selectedInfo", "clearSelection", OnClearSelection));
		AddBinding(new TriggerBinding<Entity>("selectedInfo", "setSelectedRoute", OnSetSelectedRoute));
		m_UpdateState = UIUpdateState.Create(base.World, 256);
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Combine(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		if (s_CameraController != null)
		{
			OrbitCameraController orbitCameraController = s_CameraController;
			orbitCameraController.EventCameraMove = (Action)Delegate.Remove(orbitCameraController.EventCameraMove, new Action(OnCameraStoppedFollowing));
		}
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		s_CameraController = m_CameraUpdateSystem.orbitCameraController;
		if (s_CameraController != null)
		{
			if (GameManager.instance.gameMode == GameMode.Editor)
			{
				s_CameraController.mode = OrbitCameraController.Mode.Editor;
				return;
			}
			OrbitCameraController orbitCameraController = s_CameraController;
			orbitCameraController.EventCameraMove = (Action)Delegate.Combine(orbitCameraController.EventCameraMove, new Action(OnCameraStoppedFollowing));
			s_CameraController.mode = OrbitCameraController.Mode.Follow;
		}
	}
```

- `private OnSelect(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnSelect(Entity entity)
	{
		if (base.EntityManager.Exists(entity))
		{
			if (!base.EntityManager.HasComponent<Game.Events.TrafficAccident>(entity))
			{
				SetSelection(entity);
			}
			else
			{
				StartFollowing(entity);
			}
		}
	}
```

- `private OnSetSelectedRoute(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnSetSelectedRoute(Entity entity)
	{
		selectedRoute = entity;
	}
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem obj) : System.Void`  

```csharp
private void OnToolChanged(ToolBaseSystem obj)
	{
		m_UpdateState.ForceUpdate();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		RefreshSelection();
		m_SelectedEntityBinding.Update(m_SelectedEntity);
		DynamicBuffer<LayoutElement> buffer;
		if (base.EntityManager.TryGetComponent<Controller>(m_SelectedEntity, out var component))
		{
			m_SelectedTrailerControllerBinding.Update(component.m_Controller);
		}
		else if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out buffer) && buffer.Length != 0)
		{
			m_SelectedTrailerControllerBinding.Update(m_SelectedEntity);
		}
		else
		{
			m_SelectedTrailerControllerBinding.Update(Entity.Null);
		}
		m_SelectedUITagBinding.Update(m_PrefabSystem.TryGetPrefab<PrefabBase>(m_SelectedPrefab, out var prefab) ? prefab.uiTag : string.Empty);
		m_ActiveSelectionBinding.Update(m_SelectedEntity != Entity.Null);
		if (m_LastSelectedEntity != m_SelectedEntity)
		{
			ResetRouteVisibility();
			m_LastSelectedEntity = m_SelectedEntity;
			eventSelectionChanged?.Invoke(m_SelectedEntity, m_SelectedPrefab, m_SelectedPosition);
			SetBindingsDirty();
		}
		else if (base.EntityManager.HasComponent<Updated>(m_SelectedEntity) || base.EntityManager.HasComponent<BatchesUpdated>(m_SelectedEntity) || m_UpdateState.Advance())
		{
			SetBindingsDirty();
		}
		UpdateSections();
		UpdatePosition();
	}
```

- `private RefreshSelection() : System.Void`  

```csharp
private void RefreshSelection()
	{
		if (TryGetSelection(out var entity) && base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component))
		{
			Entity prefab = component.m_Prefab;
			FilterSelection(ref entity, ref prefab);
			int elementIndex = m_ToolSystem.selectedIndex;
			if (TryGetPosition(entity, base.EntityManager, ref elementIndex, out var _, out var position, out var bounds, out var _, reinterpolate: true) || base.EntityManager.HasComponent<Household>(entity))
			{
				position.y = MathUtils.Center(bounds.y);
				m_SelectedEntity = entity;
				m_SelectedPrefab = prefab;
				m_SelectedPosition = position;
				return;
			}
		}
		m_SelectedEntity = Entity.Null;
		m_SelectedPrefab = Entity.Null;
		m_SelectedPosition = float3.zero;
	}
```

- `public RequestUpdate() : System.Void`  

```csharp
public void RequestUpdate()
	{
		m_UpdateState.ForceUpdate();
	}
```

- `private ResetRouteVisibility() : System.Void`  

```csharp
private void ResetRouteVisibility()
	{
		if (TryGetTransportConfig(out var config) && m_ToolSystem.GetInfomodes(m_ToolSystem.activeInfoview)?.Find((InfomodeInfo mode) => mode.m_Mode == config.m_RoutesInfomode) == null)
		{
			m_ToolSystem.SetInfomodeActive(config.m_RoutesInfomode, active: false, 0);
		}
	}
```

- `private SetBindingsDirty() : System.Void`  

```csharp
private void SetBindingsDirty()
	{
		if (!(m_SelectedEntity == Entity.Null))
		{
			for (int i = 0; i < m_TopSections.Count; i++)
			{
				m_TopSections[i]?.RequestUpdate();
			}
			for (int j = 0; j < m_MiddleSections.Count; j++)
			{
				m_MiddleSections[j]?.RequestUpdate();
			}
			for (int k = 0; k < m_BottomSections.Count; k++)
			{
				m_BottomSections[k]?.RequestUpdate();
			}
			m_TitleSection?.RequestUpdate();
			m_LineVisualizerSection?.RequestUpdate();
			m_DeveloperSection?.RequestUpdate();
			m_HouseholdSidebarSection?.RequestUpdate();
			m_BindingsDirty = true;
		}
	}
```

- `public SetDirty() : System.Void`  

```csharp
public void SetDirty()
	{
		SetBindingsDirty();
	}
```

- `public SetRoutesVisible() : System.Void`  

```csharp
public void SetRoutesVisible()
	{
		if (TryGetTransportConfig(out var config) && m_ToolSystem.GetInfomodes(m_ToolSystem.activeInfoview)?.Find((InfomodeInfo mode) => mode.m_Mode == config.m_RoutesInfomode) == null)
		{
			m_ToolSystem.SetInfomodeActive(config.m_RoutesInfomode, active: true, 0);
		}
	}
```

- `public SetSelection(Unity.Entities.Entity entity) : System.Void`  

```csharp
public void SetSelection(Entity entity)
	{
		if (!(entity == m_SelectedEntity))
		{
			m_ToolSystem.selected = entity;
		}
	}
```

- `private StartFollowing(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void StartFollowing(Entity entity)
	{
		if (base.EntityManager.Exists(entity) && s_CameraController != null && s_CameraController.followedEntity != entity)
		{
			s_CameraController.followedEntity = entity;
			s_CameraController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
			m_CameraUpdateSystem.activeCameraController = s_CameraController;
			SetBindingsDirty();
		}
	}
```

- `private StopFollowing() : System.Void`  

```csharp
private void StopFollowing()
	{
		if (m_CameraUpdateSystem.orbitCameraController.mode == OrbitCameraController.Mode.Follow)
		{
			m_CameraUpdateSystem.orbitCameraController.followedEntity = Entity.Null;
			m_CameraUpdateSystem.gamePlayController.TryMatchPosition(m_CameraUpdateSystem.orbitCameraController);
			m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.gamePlayController;
			SetBindingsDirty();
		}
	}
```

- `public static TryGetPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, System.Int32& elementIndex, Unity.Entities.Entity& location, Unity.Mathematics.float3& position, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation, System.Boolean reinterpolate = False) : System.Boolean`  

```csharp
public static bool TryGetPosition(Entity entity, EntityManager entityManager, ref int elementIndex, out Entity location, out float3 position, out Bounds3 bounds, out quaternion rotation, bool reinterpolate = false)
	{
		location = entity;
		FilterPositionTarget(ref location, entityManager);
		Relative component;
		Game.Objects.Transform component2;
		DynamicBuffer<RouteWaypoint> buffer2;
		DynamicBuffer<LabelPosition> buffer3;
		Geometry component3;
		Icon component4;
		Game.Net.Node component5;
		if (entityManager.TryGetBuffer(location, isReadOnly: true, out DynamicBuffer<TransformFrame> buffer))
		{
			Game.Objects.Transform interpolatedPosition = GetInterpolatedPosition(location, entityManager, buffer, reinterpolate, out bounds);
			position = interpolatedPosition.m_Position;
			rotation = interpolatedPosition.m_Rotation;
		}
		else if (entityManager.TryGetComponent<Relative>(location, out component))
		{
			Game.Objects.Transform relativePosition = GetRelativePosition(location, entityManager, component, reinterpolate, out bounds);
			position = relativePosition.m_Position;
			rotation = relativePosition.m_Rotation;
		}
		else if (entityManager.TryGetComponent<Game.Objects.Transform>(location, out component2))
		{
			Game.Objects.Transform objectPosition = GetObjectPosition(location, entityManager, component2, out bounds);
			position = objectPosition.m_Position;
			rotation = objectPosition.m_Rotation;
		}
		else if (entityManager.TryGetBuffer(location, isReadOnly: true, out buffer2))
		{
			position = GetRoutePosition(entityManager, buffer2);
			bounds = new Bounds3(position, position);
			rotation = quaternion.identity;
		}
		else if (entityManager.TryGetBuffer(location, isReadOnly: true, out buffer3))
		{
			position = GetAggregatePosition(buffer3, ref elementIndex);
			bounds = new Bounds3(position, position);
			rotation = quaternion.identity;
		}
		else if (entityManager.TryGetComponent<Geometry>(location, out component3))
		{
			position = component3.m_CenterPosition;
			bounds = new Bounds3(position, position);
			rotation = quaternion.identity;
		}
		else if (entityManager.TryGetComponent<Icon>(location, out component4))
		{
			position = component4.m_Location;
			bounds = new Bounds3(position, position);
			rotation = quaternion.identity;
		}
		else if (entityManager.TryGetComponent<Game.Net.Node>(location, out component5))
		{
			position = GetNodePosition(location, entityManager, component5, out bounds, out rotation);
		}
		else
		{
			if (!entityManager.TryGetComponent<Curve>(location, out var component6))
			{
				position = float3.zero;
				bounds = default(Bounds3);
				rotation = quaternion.identity;
				return false;
			}
			position = GetCurvePosition(location, entityManager, component6, out bounds, out rotation);
		}
		return true;
	}
```

- `private TryGetSelection(Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
private bool TryGetSelection(out Entity entity)
	{
		entity = m_ToolSystem.selected;
		return entity != Entity.Null;
	}
```

- `private TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config) : System.Boolean`  

```csharp
private bool TryGetTransportConfig(out UITransportConfigurationPrefab config)
	{
		return m_PrefabSystem.TryGetSingletonPrefab<UITransportConfigurationPrefab>(m_TransportConfigQuery, out config);
	}
```

- `private UpdatePosition() : System.Void`  

```csharp
private void UpdatePosition()
	{
		if (!(m_SelectedEntity == Entity.Null))
		{
			Vector2 vector = ((Camera.main == null) ? default(Vector3) : Camera.main.WorldToViewportPoint(selectedPosition));
			m_PositionBinding.Update(vector);
		}
	}
```

- `private UpdateSectionBindings() : System.Void`  

```csharp
private void UpdateSectionBindings()
	{
		m_TooltipTagsBinding.Update();
		m_IDSectionBinding.Update();
		m_DeveloperSectionBinding.Update();
		m_TopSectionsBinding.Update();
		m_MiddleSectionsBinding.Update();
		m_BottomSectionsBinding.Update();
		m_HouseholdSidebarSectionBinding.Update();
	}
```

- `private UpdateSections() : System.Void`  

```csharp
private void UpdateSections()
	{
		if (!(m_SelectedEntity == Entity.Null))
		{
			tooltipTags.Clear();
			m_TitleSection?.PerformUpdate();
			m_HouseholdSidebarSection?.PerformUpdate();
			m_LineVisualizerSection?.PerformUpdate();
			m_LineVisualizerSectionBinding.Update();
			for (int i = 0; i < m_TopSections.Count; i++)
			{
				m_TopSections[i]?.PerformUpdate();
			}
			for (int j = 0; j < m_MiddleSections.Count; j++)
			{
				m_MiddleSections[j]?.PerformUpdate();
			}
			for (int k = 0; k < m_BottomSections.Count; k++)
			{
				m_BottomSections[k]?.PerformUpdate();
			}
			if (m_DebugUISystem.developerInfoVisible)
			{
				m_DeveloperSection?.PerformUpdate();
			}
			if (m_BindingsDirty)
			{
				UpdateSectionBindings();
				m_BindingsDirty = false;
			}
		}
	}
```

- `private WriteDeveloperSection(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void WriteDeveloperSection(IJsonWriter binder)
	{
		if (m_DebugUISystem.developerInfoVisible)
		{
			m_DeveloperSection.Write(binder);
		}
		else
		{
			binder.WriteNull();
		}
	}
```

- `private WriteSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> list, Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void WriteSections(List<ISectionSource> list, IJsonWriter binder)
	{
		binder.ArrayBegin(list.Count);
		for (int i = 0; i < list.Count; i++)
		{
			binder.Write(list[i]);
		}
		binder.ArrayEnd();
	}
```

- `private WriteTooltipFlags(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteTooltipFlags(IJsonWriter writer)
	{
		writer.ArrayBegin(tooltipTags.Count);
		for (int i = 0; i < tooltipTags.Count; i++)
		{
			writer.Write(tooltipTags[i].ToString());
		}
		writer.ArrayEnd();
	}
```


## Nested types

- `Game.UI.InGame.SelectedInfoUISystem+<>c__DisplayClass73_0`  
- `Game.UI.InGame.SelectedInfoUISystem+<>c__DisplayClass74_0`  

