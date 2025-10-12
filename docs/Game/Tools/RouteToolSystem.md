# Game.Tools.RouteToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <underground>k__BackingField`  
- `private System.Boolean <serviceUpgrade>k__BackingField`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_TempRouteQuery`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Game.Input.IProxyAction m_AddWaypoint`  
- `private Game.Input.IProxyAction m_InsertWaypoint`  
- `private Game.Input.IProxyAction m_MoveWaypoint`  
- `private Game.Input.IProxyAction m_MergeWaypoint`  
- `private Game.Input.IProxyAction m_RemoveWaypoint`  
- `private Game.Input.IProxyAction m_UndoWaypoint`  
- `private Game.Input.IProxyAction m_CreateRoute`  
- `private Game.Input.IProxyAction m_CompleteRoute`  
- `private Game.Input.IProxyAction m_DeleteRoute`  
- `private Game.Input.IProxyAction m_DiscardInsertWaypoint`  
- `private Game.Input.IProxyAction m_DiscardMoveWaypoint`  
- `private Game.Input.IProxyAction m_DiscardMergeWaypoint`  
- `private System.Boolean m_ApplyBlocked`  
- `private Game.Tools.ControlPoint m_LastRaycastPoint`  
- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  
- `private Colossal.Collections.NativeValue<Game.Tools.RouteToolSystem+Tooltip> m_Tooltip`  
- `private Game.Tools.RouteToolSystem+State m_State`  
- `private System.Boolean m_ControlPointsMoved`  
- `private System.Boolean m_ForceApply`  
- `private System.Boolean m_ForceCancel`  
- `private System.Boolean m_CanApplyModify`  
- `private Game.Tools.ControlPoint m_MoveStartPosition`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Prefabs.RoutePrefab m_SelectedPrefab`  
- `private Game.Tools.RouteToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public Game.Prefabs.RoutePrefab prefab { get; set }`  
- `public Game.Tools.RouteToolSystem+State state { get }`  
- `public Game.Tools.ControlPoint moveStartPosition { get }`  
- `public Game.Tools.RouteToolSystem+Tooltip tooltip { get }`  
- `public System.Boolean underground { get; set }`  
- `public System.Boolean serviceUpgrade { get; private set }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

## Constructors

- `public RouteToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private CheckPathUpdates() : System.Boolean`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual ElevationDown() : System.Void`  
- `public virtual ElevationScroll() : System.Void`  
- `public virtual ElevationUp() : System.Void`  
- `public GetControlPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  
- `private GetPathfindCompleted() : System.Boolean`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  
- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual SetUnderground(System.Boolean underground) : System.Void`  
- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute) : Unity.Jobs.JobHandle`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateApplyAction() : System.Void`  
- `private UpdateCancelAction() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute) : Unity.Jobs.JobHandle`  
- `private UpdateSecondaryApplyAction() : System.Void`  

## Nested types

- `Game.Tools.RouteToolSystem+State`  
- `Game.Tools.RouteToolSystem+Tooltip`  
- `Game.Tools.RouteToolSystem+SnapJob`  
- `Game.Tools.RouteToolSystem+CreateDefinitionsJob`  
- `Game.Tools.RouteToolSystem+TypeHandle`  
- `Game.Tools.RouteToolSystem+<get_toolActions>d__41`  

