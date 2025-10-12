# Game.Tools.ToolBaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private UnityEngine.Color32 <color>k__BackingField`  
- `private Game.Prefabs.BrushPrefab <brushType>k__BackingField`  
- `private System.Single <brushSize>k__BackingField`  
- `private System.Single <brushAngle>k__BackingField`  
- `private System.Single <brushStrength>k__BackingField`  
- `private System.Boolean <requireZones>k__BackingField`  
- `private System.Boolean <requireUnderground>k__BackingField`  
- `private System.Boolean <requirePipelines>k__BackingField`  
- `private System.Boolean <requireNetArrows>k__BackingField`  
- `private System.Boolean <requireStopIcons>k__BackingField`  
- `private Game.Areas.AreaTypeMask <requireAreas>k__BackingField`  
- `private Game.Routes.RouteType <requireRoutes>k__BackingField`  
- `private Game.Prefabs.TransportType <requireStops>k__BackingField`  
- `private Game.Net.Layer <requireNet>k__BackingField`  
- `private Game.Prefabs.InfoviewPrefab <infoview>k__BackingField`  
- `private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> <infomodes>k__BackingField`  
- `private Game.Tools.Snap <selectedSnap>k__BackingField`  
- `private Game.Tools.ApplyMode <applyMode>k__BackingField`  
- `private System.Boolean <allowUnderground>k__BackingField`  
- `protected Game.Tools.ToolSystem m_ToolSystem`  
- `protected Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `protected Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `protected Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  
- `protected Game.Tools.OriginalDeletedSystem m_OriginalDeletedSystem`  
- `protected Unity.Entities.EntityQuery m_ErrorQuery`  
- `protected Game.Tools.Snap m_SnapOnMask`  
- `protected Game.Tools.Snap m_SnapOffMask`  
- `protected System.Boolean m_HasFocus`  
- `protected System.Boolean m_FocusChanged`  
- `protected System.Boolean m_ForceUpdate`  
- `private Game.Input.IProxyAction m_ApplyAction`  
- `private Game.Input.IProxyAction m_SecondaryApplyAction`  
- `private Game.Input.IProxyAction m_CancelAction`  
- `private System.Boolean <actionsEnabled>k__BackingField`  
- `private Game.Tools.ToolBaseSystem+TypeHandle __TypeHandle`  
- `private static System.Action<Game.Input.ProxyAction> EventToolActionPerformed`  
- `public static const Game.Tools.Snap kSnapAllIgnoredMask`  

## Properties

- `public System.String toolID { get }`  
- `public System.Int32 uiModeIndex { get }`  
- `public UnityEngine.Color32 color { get; set }`  
- `public Game.Prefabs.BrushPrefab brushType { get; set }`  
- `public System.Single brushSize { get; set }`  
- `public System.Single brushAngle { get; set }`  
- `public System.Single brushStrength { get; set }`  
- `public System.Boolean requireZones { get; protected set }`  
- `public System.Boolean requireUnderground { get; protected set }`  
- `public System.Boolean requirePipelines { get; protected set }`  
- `public System.Boolean requireNetArrows { get; protected set }`  
- `public System.Boolean requireStopIcons { get; protected set }`  
- `public Game.Areas.AreaTypeMask requireAreas { get; protected set }`  
- `public Game.Routes.RouteType requireRoutes { get; protected set }`  
- `public Game.Prefabs.TransportType requireStops { get; protected set }`  
- `public Game.Net.Layer requireNet { get; protected set }`  
- `public Game.Prefabs.InfoviewPrefab infoview { get; private set }`  
- `public System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes { get; private set }`  
- `public Game.Tools.Snap selectedSnap { get; set }`  
- `public Game.Tools.ApplyMode applyMode { get; protected set }`  
- `public System.Boolean allowUnderground { get; protected set }`  
- `public System.Boolean brushing { get }`  
- `protected Game.Input.IProxyAction applyAction { protected get }`  
- `protected Game.Input.IProxyAction secondaryApplyAction { protected get }`  
- `protected Game.Input.IProxyAction cancelAction { protected get }`  
- `protected Game.Input.IProxyAction applyActionOverride { protected get; protected set }`  
- `protected Game.Input.IProxyAction secondaryApplyActionOverride { protected get; protected set }`  
- `protected Game.Input.IProxyAction cancelActionOverride { protected get; protected set }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> baseToolActions { private get }`  
- `internal System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> actions { internal get }`  
- `private System.Boolean actionsEnabled { private get; private set }`  

## Constructors

- `protected ToolBaseSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected DestroyDefinitions(Unity.Entities.EntityQuery group, Game.Tools.ToolOutputBarrier barrier, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual ElevationDown() : System.Void`  
- `public virtual ElevationScroll() : System.Void`  
- `public virtual ElevationUp() : System.Void`  
- `protected EnsureCachedBrushData() : System.Void`  
- `public Equals(Game.Tools.ToolBaseSystem other) : System.Boolean`  
- `protected FindDefaultBrush(Unity.Entities.EntityQuery query) : Game.Prefabs.BrushPrefab`  
- `public static GetActualSnap(Game.Tools.Snap selectedSnap, Game.Tools.Snap onMask, Game.Tools.Snap offMask) : Game.Tools.Snap`  
- `protected GetActualSnap() : Game.Tools.Snap`  
- `protected virtual GetAllowApply() : System.Boolean`  
- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `protected GetBrushQuery() : Unity.Entities.EntityQuery`  
- `protected GetContainerQuery() : Unity.Entities.EntityQuery`  
- `protected GetContainers(Unity.Entities.EntityQuery group, Unity.Entities.Entity& laneContainer, Unity.Entities.Entity& transformContainer) : System.Boolean`  
- `protected GetDefinitionQuery() : Unity.Entities.EntityQuery`  
- `public abstract GetPrefab() : Game.Prefabs.PrefabBase`  
- `protected GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit) : System.Boolean`  
- `protected GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit, System.Boolean& forceUpdate) : System.Boolean`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  
- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected InvertBrushes(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private OnActionInteraction(Game.Input.ProxyAction action, UnityEngine.InputSystem.InputActionPhase phase) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnFocusChanged(System.Boolean hasfocus) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected OnUpdate() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private virtual ResetActions() : System.Void`  
- `protected SetAction(Game.Input.IProxyAction& action, Game.Input.IProxyAction newAction) : System.Void`  
- `private virtual SetActions() : System.Void`  
- `private SetInteraction(System.Boolean set) : System.Void`  
- `public virtual SetUnderground(System.Boolean underground) : System.Void`  
- `public ToggleToolOptions(System.Boolean enabled) : System.Void`  
- `public abstract TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private virtual UpdateActions() : System.Void`  
- `protected UpdateInfoview(Unity.Entities.Entity prefab) : System.Void`  

## Events

- `EventToolActionPerformed` : `System.Action<Game.Input.ProxyAction>`  

## Nested types

- `Game.Tools.ToolBaseSystem+DestroyDefinitionsJob`  
- `Game.Tools.ToolBaseSystem+InvertBrushesJob`  
- `Game.Tools.ToolBaseSystem+TypeHandle`  
- `Game.Tools.ToolBaseSystem+<get_baseToolActions>d__124`  
- `Game.Tools.ToolBaseSystem+<get_toolActions>d__122`  

