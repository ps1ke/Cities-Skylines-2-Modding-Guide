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
public SelectedInfoUISystem();
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
public System.Void AddBottomSection(Game.UI.InGame.ISectionSource section);
```

- `public AddDeveloperInfo(Game.UI.InGame.ISubsectionSource subsection) : System.Void`  

```csharp
public System.Void AddDeveloperInfo(Game.UI.InGame.ISubsectionSource subsection);
```

- `public AddMiddleSection(Game.UI.InGame.ISectionSource section) : System.Void`  

```csharp
public System.Void AddMiddleSection(Game.UI.InGame.ISectionSource section);
```

- `private AddSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> topSections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> sections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> bottomSections) : System.Void`  

```csharp
private System.Void AddSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> topSections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> sections, System.Collections.Generic.List<Game.UI.InGame.ISectionSource> bottomSections);
```

- `public AddTopSection(Game.UI.InGame.ISectionSource section) : System.Void`  

```csharp
public System.Void AddTopSection(Game.UI.InGame.ISectionSource section);
```

- `private static FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.EntityManager entityManager) : System.Void`  

```csharp
private static System.Void FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.EntityManager entityManager);
```

- `private static FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.Entity location, Unity.Entities.EntityManager entityManager) : System.Void`  

```csharp
private static System.Void FilterPositionTarget(Unity.Entities.Entity& entity, Unity.Entities.Entity location, Unity.Entities.EntityManager entityManager);
```

- `private FilterSelection(Unity.Entities.Entity& entity, Unity.Entities.Entity& prefab) : System.Void`  

```csharp
private System.Void FilterSelection(Unity.Entities.Entity& entity, Unity.Entities.Entity& prefab);
```

- `public Focus(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Focus(Unity.Entities.Entity entity);
```

- `private static GetAggregatePosition(Unity.Entities.DynamicBuffer<Game.Net.LabelPosition> labelPositions, System.Int32& selectedIndex) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 GetAggregatePosition(Unity.Entities.DynamicBuffer<Game.Net.LabelPosition> labelPositions, System.Int32& selectedIndex);
```

- `private static GetCurvePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Curve curve, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 GetCurvePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Curve curve, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation);
```

- `private static GetInterpolatedPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Objects.TransformFrame> transformFrames, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  

```csharp
private static Game.Objects.Transform GetInterpolatedPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Objects.TransformFrame> transformFrames, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds);
```

- `private static GetNodePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Node node, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 GetNodePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Net.Node node, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation);
```

- `private static GetObjectPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Transform transform, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  

```csharp
private static Game.Objects.Transform GetObjectPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Transform transform, Colossal.Mathematics.Bounds3& bounds);
```

- `private static GetRelativePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Relative relative, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds) : Game.Objects.Transform`  

```csharp
private static Game.Objects.Transform GetRelativePosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Objects.Relative relative, System.Boolean reinterpolate, Colossal.Mathematics.Bounds3& bounds);
```

- `private static GetRoutePosition(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> routeWaypoints) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 GetRoutePosition(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> routeWaypoints);
```

- `private static IsNearCamera(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager) : System.Boolean`  

```csharp
private static System.Boolean IsNearCamera(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager);
```

- `private OnCameraStoppedFollowing() : System.Void`  

```csharp
private System.Void OnCameraStoppedFollowing();
```

- `private OnClearSelection() : System.Void`  

```csharp
private System.Void OnClearSelection();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnSelect(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void OnSelect(Unity.Entities.Entity entity);
```

- `private OnSetSelectedRoute(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void OnSetSelectedRoute(Unity.Entities.Entity entity);
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem obj) : System.Void`  

```csharp
private System.Void OnToolChanged(Game.Tools.ToolBaseSystem obj);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private RefreshSelection() : System.Void`  

```csharp
private System.Void RefreshSelection();
```

- `public RequestUpdate() : System.Void`  

```csharp
public System.Void RequestUpdate();
```

- `private ResetRouteVisibility() : System.Void`  

```csharp
private System.Void ResetRouteVisibility();
```

- `private SetBindingsDirty() : System.Void`  

```csharp
private System.Void SetBindingsDirty();
```

- `public SetDirty() : System.Void`  

```csharp
public System.Void SetDirty();
```

- `public SetRoutesVisible() : System.Void`  

```csharp
public System.Void SetRoutesVisible();
```

- `public SetSelection(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void SetSelection(Unity.Entities.Entity entity);
```

- `private StartFollowing(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void StartFollowing(Unity.Entities.Entity entity);
```

- `private StopFollowing() : System.Void`  

```csharp
private System.Void StopFollowing();
```

- `public static TryGetPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, System.Int32& elementIndex, Unity.Entities.Entity& location, Unity.Mathematics.float3& position, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation, System.Boolean reinterpolate = False) : System.Boolean`  

```csharp
public static System.Boolean TryGetPosition(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, System.Int32& elementIndex, Unity.Entities.Entity& location, Unity.Mathematics.float3& position, Colossal.Mathematics.Bounds3& bounds, Unity.Mathematics.quaternion& rotation, System.Boolean reinterpolate);
```

- `private TryGetSelection(Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
private System.Boolean TryGetSelection(Unity.Entities.Entity& entity);
```

- `private TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config) : System.Boolean`  

```csharp
private System.Boolean TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config);
```

- `private UpdatePosition() : System.Void`  

```csharp
private System.Void UpdatePosition();
```

- `private UpdateSectionBindings() : System.Void`  

```csharp
private System.Void UpdateSectionBindings();
```

- `private UpdateSections() : System.Void`  

```csharp
private System.Void UpdateSections();
```

- `private WriteDeveloperSection(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void WriteDeveloperSection(Colossal.UI.Binding.IJsonWriter binder);
```

- `private WriteSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> list, Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void WriteSections(System.Collections.Generic.List<Game.UI.InGame.ISectionSource> list, Colossal.UI.Binding.IJsonWriter binder);
```

- `private WriteTooltipFlags(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteTooltipFlags(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.InGame.SelectedInfoUISystem+<>c__DisplayClass73_0`  
- `Game.UI.InGame.SelectedInfoUISystem+<>c__DisplayClass74_0`  

