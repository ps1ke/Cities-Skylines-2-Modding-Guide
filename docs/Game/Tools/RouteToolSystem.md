# Game.Tools.RouteToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <serviceUpgrade>k__BackingField;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_TempRouteQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Input.IProxyAction m_AddWaypoint;
    private Game.Input.IProxyAction m_InsertWaypoint;
    private Game.Input.IProxyAction m_MoveWaypoint;
    private Game.Input.IProxyAction m_MergeWaypoint;
    private Game.Input.IProxyAction m_RemoveWaypoint;
    private Game.Input.IProxyAction m_UndoWaypoint;
    private Game.Input.IProxyAction m_CreateRoute;
    private Game.Input.IProxyAction m_CompleteRoute;
    private Game.Input.IProxyAction m_DeleteRoute;
    private Game.Input.IProxyAction m_DiscardInsertWaypoint;
    private Game.Input.IProxyAction m_DiscardMoveWaypoint;
    private Game.Input.IProxyAction m_DiscardMergeWaypoint;
    private System.Boolean m_ApplyBlocked;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Colossal.Collections.NativeValue<Game.Tools.RouteToolSystem+Tooltip> m_Tooltip;
    private Game.Tools.RouteToolSystem+State m_State;
    private System.Boolean m_ControlPointsMoved;
    private System.Boolean m_ForceApply;
    private System.Boolean m_ForceCancel;
    private System.Boolean m_CanApplyModify;
    private Game.Tools.ControlPoint m_MoveStartPosition;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Prefabs.RoutePrefab m_SelectedPrefab;
    private Game.Tools.RouteToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public Game.Prefabs.RoutePrefab prefab { get; set; }
    public Game.Tools.RouteToolSystem+State state { get; }
    public Game.Tools.ControlPoint moveStartPosition { get; }
    public Game.Tools.RouteToolSystem+Tooltip tooltip { get; }
    public System.Boolean underground { get; set; }
    public System.Boolean serviceUpgrade { get; private set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public RouteToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private System.Boolean CheckPathUpdates();
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Jobs.JobHandle& dependencies);
    private System.Boolean GetPathfindCompleted();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private System.Void UpdateApplyAction();
    private System.Void UpdateCancelAction();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute);
    private System.Void UpdateSecondaryApplyAction();
}
```


## Fields

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <serviceUpgrade>k__BackingField`  

```csharp
private System.Boolean <serviceUpgrade>k__BackingField;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_TempRouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempRouteQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Input.IProxyAction m_AddWaypoint`  

```csharp
private Game.Input.IProxyAction m_AddWaypoint;
```

- `private Game.Input.IProxyAction m_InsertWaypoint`  

```csharp
private Game.Input.IProxyAction m_InsertWaypoint;
```

- `private Game.Input.IProxyAction m_MoveWaypoint`  

```csharp
private Game.Input.IProxyAction m_MoveWaypoint;
```

- `private Game.Input.IProxyAction m_MergeWaypoint`  

```csharp
private Game.Input.IProxyAction m_MergeWaypoint;
```

- `private Game.Input.IProxyAction m_RemoveWaypoint`  

```csharp
private Game.Input.IProxyAction m_RemoveWaypoint;
```

- `private Game.Input.IProxyAction m_UndoWaypoint`  

```csharp
private Game.Input.IProxyAction m_UndoWaypoint;
```

- `private Game.Input.IProxyAction m_CreateRoute`  

```csharp
private Game.Input.IProxyAction m_CreateRoute;
```

- `private Game.Input.IProxyAction m_CompleteRoute`  

```csharp
private Game.Input.IProxyAction m_CompleteRoute;
```

- `private Game.Input.IProxyAction m_DeleteRoute`  

```csharp
private Game.Input.IProxyAction m_DeleteRoute;
```

- `private Game.Input.IProxyAction m_DiscardInsertWaypoint`  

```csharp
private Game.Input.IProxyAction m_DiscardInsertWaypoint;
```

- `private Game.Input.IProxyAction m_DiscardMoveWaypoint`  

```csharp
private Game.Input.IProxyAction m_DiscardMoveWaypoint;
```

- `private Game.Input.IProxyAction m_DiscardMergeWaypoint`  

```csharp
private Game.Input.IProxyAction m_DiscardMergeWaypoint;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Colossal.Collections.NativeValue<Game.Tools.RouteToolSystem+Tooltip> m_Tooltip`  

```csharp
private Colossal.Collections.NativeValue<Game.Tools.RouteToolSystem+Tooltip> m_Tooltip;
```

- `private Game.Tools.RouteToolSystem+State m_State`  

```csharp
private Game.Tools.RouteToolSystem+State m_State;
```

- `private System.Boolean m_ControlPointsMoved`  

```csharp
private System.Boolean m_ControlPointsMoved;
```

- `private System.Boolean m_ForceApply`  

```csharp
private System.Boolean m_ForceApply;
```

- `private System.Boolean m_ForceCancel`  

```csharp
private System.Boolean m_ForceCancel;
```

- `private System.Boolean m_CanApplyModify`  

```csharp
private System.Boolean m_CanApplyModify;
```

- `private Game.Tools.ControlPoint m_MoveStartPosition`  

```csharp
private Game.Tools.ControlPoint m_MoveStartPosition;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Prefabs.RoutePrefab m_SelectedPrefab`  

```csharp
private Game.Prefabs.RoutePrefab m_SelectedPrefab;
```

- `private Game.Tools.RouteToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.RouteToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```


## Properties

- `public System.String toolID { get }`  

```csharp
public System.String toolID { get; }
```

- `public Game.Prefabs.RoutePrefab prefab { get; set }`  

```csharp
public Game.Prefabs.RoutePrefab prefab { get; set; }
```

- `public Game.Tools.RouteToolSystem+State state { get }`  

```csharp
public Game.Tools.RouteToolSystem+State state { get; }
```

- `public Game.Tools.ControlPoint moveStartPosition { get }`  

```csharp
public Game.Tools.ControlPoint moveStartPosition { get; }
```

- `public Game.Tools.RouteToolSystem+Tooltip tooltip { get }`  

```csharp
public Game.Tools.RouteToolSystem+Tooltip tooltip { get; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean serviceUpgrade { get; private set }`  

```csharp
public System.Boolean serviceUpgrade { get; private set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public RouteToolSystem()`  

```csharp
public RouteToolSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
```

- `private CheckPathUpdates() : System.Boolean`  

```csharp
private System.Boolean CheckPathUpdates();
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
```

- `public virtual ElevationDown() : System.Void`  

```csharp
public virtual System.Void ElevationDown();
```

- `public virtual ElevationScroll() : System.Void`  

```csharp
public virtual System.Void ElevationScroll();
```

- `public virtual ElevationUp() : System.Void`  

```csharp
public virtual System.Void ElevationUp();
```

- `public GetControlPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  

```csharp
public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Jobs.JobHandle& dependencies);
```

- `private GetPathfindCompleted() : System.Boolean`  

```csharp
private System.Boolean GetPathfindCompleted();
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public virtual Game.Prefabs.PrefabBase GetPrefab();
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
```

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public virtual System.Void InitializeRaycast();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public virtual System.Void SetUnderground(System.Boolean underground);
```

- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute);
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
```

- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private virtual System.Void UpdateActions();
```

- `private UpdateApplyAction() : System.Void`  

```csharp
private System.Void UpdateApplyAction();
```

- `private UpdateCancelAction() : System.Void`  

```csharp
private System.Void UpdateCancelAction();
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute);
```

- `private UpdateSecondaryApplyAction() : System.Void`  

```csharp
private System.Void UpdateSecondaryApplyAction();
```


## Nested types

- `Game.Tools.RouteToolSystem+State`  
- `Game.Tools.RouteToolSystem+Tooltip`  
- `Game.Tools.RouteToolSystem+SnapJob`  
- `Game.Tools.RouteToolSystem+CreateDefinitionsJob`  
- `Game.Tools.RouteToolSystem+TypeHandle`  
- `Game.Tools.RouteToolSystem+<get_toolActions>d__41`  

