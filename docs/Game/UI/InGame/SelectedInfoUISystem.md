# Game.UI.InGame.SelectedInfoUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Unity.Mathematics.float3> <eventSelectionChanged>k__BackingField`  
- `private System.Collections.Generic.List<Game.UI.InGame.TooltipTags> <tooltipTags>k__BackingField`  
- `private Unity.Mathematics.float3 m_SelectedPosition`  
- `private Unity.Entities.Entity m_SelectedEntity`  
- `private Unity.Entities.Entity m_SelectedPrefab`  
- `private Unity.Entities.Entity m_SelectedRoute`  
- `private Unity.Entities.Entity m_LastSelectedEntity`  
- `private Unity.Entities.EntityQuery m_TransportConfigQuery`  
- `private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_TopSections`  
- `private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_MiddleSections`  
- `private System.Collections.Generic.List<Game.UI.InGame.ISectionSource> m_BottomSections`  
- `private Game.UI.InGame.TitleSection m_TitleSection`  
- `private Game.UI.InGame.DeveloperSection m_DeveloperSection`  
- `private Game.UI.InGame.LineVisualizerSection m_LineVisualizerSection`  
- `private Game.UI.InGame.HouseholdSidebarSection m_HouseholdSidebarSection`  
- `private Game.UI.Debug.DebugUISystem m_DebugUISystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedEntityBinding`  
- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedTrailerControllerBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedUITagBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_SelectedRouteBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveSelectionBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_TopSectionsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_MiddleSectionsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_BottomSectionsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_IDSectionBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_LineVisualizerSectionBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_DeveloperSectionBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_HouseholdSidebarSectionBinding`  
- `private Colossal.UI.Binding.ValueBinding<Unity.Mathematics.float2> m_PositionBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_TooltipTagsBinding`  
- `private System.Boolean m_BindingsDirty`  
- `private Game.UI.UIUpdateState m_UpdateState`  
- `public static Game.OrbitCameraController s_CameraController`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `public Unity.Mathematics.float3 selectedPosition { get }`  
- `public Unity.Entities.Entity selectedEntity { get }`  
- `public Unity.Entities.Entity selectedPrefab { get }`  
- `public Unity.Entities.Entity selectedRoute { get; set }`  
- `public System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Unity.Mathematics.float3> eventSelectionChanged { get; set }`  
- `public System.Collections.Generic.List<Game.UI.InGame.TooltipTags> tooltipTags { get; set }`  

## Constructors

- `public SelectedInfoUISystem()`  

## Methods

- `private <OnCreate>b__54_0() : Unity.Entities.Entity`  
- `private <OnCreate>b__54_1(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private <OnCreate>b__54_2(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private <OnCreate>b__54_3(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private <OnCreate>b__54_4(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private <OnCreate>b__54_5(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private <OnCreate>b__54_6(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public AddBottomSection(Game.UI.InGame.ISectionSource section) : System.Void`  
- `public AddDeveloperInfo(Game.UI.InGame.ISubsectionSource subsection) : System.Void`  
- `public AddMiddleSection(Game.UI.InGame.ISectionSource section) : System.Void`  
- `private AddSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> topSections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> sections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> bottomSections) : System.Void`  
- `public AddTopSection(Game.UI.InGame.ISectionSource section) : System.Void`  
- `private static FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.EntityManager entityManager) : System.Void`  
- `private static FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.Entity location, Unity.Entities.EntityManager entityManager) : System.Void`  
- `private FilterSelection(Unity.Entities.Entity& entity, Unity.Entities.Entity& prefab) : System.Void`  
- `public Focus(Unity.Entities.Entity entity) : System.Void`  
- `private static GetAggregatePosition(Unity.Entities.DynamicBuffer<Game.Net.LabelPosition> labelPositions, System.Int32& selectedIndex) : Unity.Mathematics.float3`  
- `private static GetCurvePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Curve curve, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation) : Unity.Mathematics.float3`  
- `private static GetInterpolatedPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Objects.TransformFrame> transformFrames, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  
- `private static GetNodePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Node node, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation) : Unity.Mathematics.float3`  
- `private static GetObjectPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Transform transform, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  
- `private static GetRelativePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Relative relative, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  
- `private static GetRoutePosition(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> routeWaypoints) : Unity.Mathematics.float3`  
- `private static IsNearCamera(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager) : System.Boolean`  
- `private OnCameraStoppedFollowing() : System.Void`  
- `private OnClearSelection() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnSelect(Unity.Entities.Entity entity) : System.Void`  
- `private OnSetSelectedRoute(Unity.Entities.Entity entity) : System.Void`  
- `private OnToolChanged(Game.Tools.ToolBaseSystem obj) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RefreshSelection() : System.Void`  
- `public RequestUpdate() : System.Void`  
- `private ResetRouteVisibility() : System.Void`  
- `private SetBindingsDirty() : System.Void`  
- `public SetDirty() : System.Void`  
- `public SetRoutesVisible() : System.Void`  
- `public SetSelection(Unity.Entities.Entity entity) : System.Void`  
- `private StartFollowing(Unity.Entities.Entity entity) : System.Void`  
- `private StopFollowing() : System.Void`  
- `public static TryGetPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, System.Int32& elementIndex, Unity.Entities.Entity& location, Unity.Mathematics.float3& position, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation, System.Boolean reinterpolate = False) : System.Boolean`  
- `private TryGetSelection(Unity.Entities.Entity& entity) : System.Boolean`  
- `private TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config) : System.Boolean`  
- `private UpdatePosition() : System.Void`  
- `private UpdateSectionBindings() : System.Void`  
- `private UpdateSections() : System.Void`  
- `private WriteDeveloperSection(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private WriteSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> list, Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private WriteTooltipFlags(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.InGame.SelectedInfoUISystem+<>c__DisplayClass73_0`  
- `Game.UI.InGame.SelectedInfoUISystem+<>c__DisplayClass74_0`  

