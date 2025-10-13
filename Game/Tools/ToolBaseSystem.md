# Game.Tools.ToolBaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public abstract class ToolBaseSystem : Game.GameSystemBase, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private UnityEngine.Color32 <color>k__BackingField;
    private Game.Prefabs.BrushPrefab <brushType>k__BackingField;
    private System.Single <brushSize>k__BackingField;
    private System.Single <brushAngle>k__BackingField;
    private System.Single <brushStrength>k__BackingField;
    private System.Boolean <requireZones>k__BackingField;
    private System.Boolean <requireUnderground>k__BackingField;
    private System.Boolean <requirePipelines>k__BackingField;
    private System.Boolean <requireNetArrows>k__BackingField;
    private System.Boolean <requireStopIcons>k__BackingField;
    private Game.Areas.AreaTypeMask <requireAreas>k__BackingField;
    private Game.Routes.RouteType <requireRoutes>k__BackingField;
    private Game.Prefabs.TransportType <requireStops>k__BackingField;
    private Game.Net.Layer <requireNet>k__BackingField;
    private Game.Prefabs.InfoviewPrefab <infoview>k__BackingField;
    private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> <infomodes>k__BackingField;
    private Game.Tools.Snap <selectedSnap>k__BackingField;
    private Game.Tools.ApplyMode <applyMode>k__BackingField;
    private System.Boolean <allowUnderground>k__BackingField;
    protected Game.Tools.ToolSystem m_ToolSystem;
    protected Game.Prefabs.PrefabSystem m_PrefabSystem;
    protected Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    protected Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    protected Game.Tools.OriginalDeletedSystem m_OriginalDeletedSystem;
    protected Unity.Entities.EntityQuery m_ErrorQuery;
    protected Game.Tools.Snap m_SnapOnMask;
    protected Game.Tools.Snap m_SnapOffMask;
    protected System.Boolean m_HasFocus;
    protected System.Boolean m_FocusChanged;
    protected System.Boolean m_ForceUpdate;
    private Game.Input.IProxyAction m_ApplyAction;
    private Game.Input.IProxyAction m_SecondaryApplyAction;
    private Game.Input.IProxyAction m_CancelAction;
    private System.Boolean <actionsEnabled>k__BackingField;
    private Game.Tools.ToolBaseSystem+TypeHandle __TypeHandle;
    private static System.Action<Game.Input.ProxyAction> EventToolActionPerformed;
    public static const Game.Tools.Snap kSnapAllIgnoredMask;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public UnityEngine.Color32 color { get; set; }
    public Game.Prefabs.BrushPrefab brushType { get; set; }
    public System.Single brushSize { get; set; }
    public System.Single brushAngle { get; set; }
    public System.Single brushStrength { get; set; }
    public System.Boolean requireZones { get; protected set; }
    public System.Boolean requireUnderground { get; protected set; }
    public System.Boolean requirePipelines { get; protected set; }
    public System.Boolean requireNetArrows { get; protected set; }
    public System.Boolean requireStopIcons { get; protected set; }
    public Game.Areas.AreaTypeMask requireAreas { get; protected set; }
    public Game.Routes.RouteType requireRoutes { get; protected set; }
    public Game.Prefabs.TransportType requireStops { get; protected set; }
    public Game.Net.Layer requireNet { get; protected set; }
    public Game.Prefabs.InfoviewPrefab infoview { get; private set; }
    public System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes { get; private set; }
    public Game.Tools.Snap selectedSnap { get; set; }
    public Game.Tools.ApplyMode applyMode { get; protected set; }
    public System.Boolean allowUnderground { get; protected set; }
    public System.Boolean brushing { get; }
    protected Game.Input.IProxyAction applyAction { protected get; }
    protected Game.Input.IProxyAction secondaryApplyAction { protected get; }
    protected Game.Input.IProxyAction cancelAction { protected get; }
    protected Game.Input.IProxyAction applyActionOverride { protected get; protected set; }
    protected Game.Input.IProxyAction secondaryApplyActionOverride { protected get; protected set; }
    protected Game.Input.IProxyAction cancelActionOverride { protected get; protected set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> baseToolActions { private get; }
    internal System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> actions { internal get; }
    private System.Boolean actionsEnabled { private get; private set; }

    protected ToolBaseSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected Unity.Jobs.JobHandle DestroyDefinitions(Unity.Entities.EntityQuery group, Game.Tools.ToolOutputBarrier barrier, Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    protected System.Void EnsureCachedBrushData();
    public System.Boolean Equals(Game.Tools.ToolBaseSystem other);
    protected Game.Prefabs.BrushPrefab FindDefaultBrush(Unity.Entities.EntityQuery query);
    public static Game.Tools.Snap GetActualSnap(Game.Tools.Snap selectedSnap, Game.Tools.Snap onMask, Game.Tools.Snap offMask);
    protected Game.Tools.Snap GetActualSnap();
    protected virtual System.Boolean GetAllowApply();
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    protected Unity.Entities.EntityQuery GetBrushQuery();
    protected Unity.Entities.EntityQuery GetContainerQuery();
    protected System.Boolean GetContainers(Unity.Entities.EntityQuery group, Unity.Entities.Entity& laneContainer, Unity.Entities.Entity& transformContainer);
    protected Unity.Entities.EntityQuery GetDefinitionQuery();
    public abstract Game.Prefabs.PrefabBase GetPrefab();
    protected System.Boolean GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit);
    protected System.Boolean GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit, System.Boolean& forceUpdate);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    public virtual System.Void InitializeRaycast();
    protected Unity.Jobs.JobHandle InvertBrushes(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
    private System.Void OnActionInteraction(Game.Input.ProxyAction action, UnityEngine.InputSystem.InputActionPhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnFocusChanged(System.Boolean hasfocus);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected System.Void OnUpdate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void ResetActions();
    protected System.Void SetAction(Game.Input.IProxyAction& action, Game.Input.IProxyAction newAction);
    private virtual System.Void SetActions();
    private System.Void SetInteraction(System.Boolean set);
    public virtual System.Void SetUnderground(System.Boolean underground);
    public System.Void ToggleToolOptions(System.Boolean enabled);
    public abstract System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private virtual System.Void UpdateActions();
    protected System.Void UpdateInfoview(Unity.Entities.Entity prefab);
}
```


## Fields

- `private UnityEngine.Color32 <color>k__BackingField`  

```csharp
private UnityEngine.Color32 <color>k__BackingField;
```

- `private Game.Prefabs.BrushPrefab <brushType>k__BackingField`  

```csharp
private Game.Prefabs.BrushPrefab <brushType>k__BackingField;
```

- `private System.Single <brushSize>k__BackingField`  

```csharp
private System.Single <brushSize>k__BackingField;
```

- `private System.Single <brushAngle>k__BackingField`  

```csharp
private System.Single <brushAngle>k__BackingField;
```

- `private System.Single <brushStrength>k__BackingField`  

```csharp
private System.Single <brushStrength>k__BackingField;
```

- `private System.Boolean <requireZones>k__BackingField`  

```csharp
private System.Boolean <requireZones>k__BackingField;
```

- `private System.Boolean <requireUnderground>k__BackingField`  

```csharp
private System.Boolean <requireUnderground>k__BackingField;
```

- `private System.Boolean <requirePipelines>k__BackingField`  

```csharp
private System.Boolean <requirePipelines>k__BackingField;
```

- `private System.Boolean <requireNetArrows>k__BackingField`  

```csharp
private System.Boolean <requireNetArrows>k__BackingField;
```

- `private System.Boolean <requireStopIcons>k__BackingField`  

```csharp
private System.Boolean <requireStopIcons>k__BackingField;
```

- `private Game.Areas.AreaTypeMask <requireAreas>k__BackingField`  

```csharp
private Game.Areas.AreaTypeMask <requireAreas>k__BackingField;
```

- `private Game.Routes.RouteType <requireRoutes>k__BackingField`  

```csharp
private Game.Routes.RouteType <requireRoutes>k__BackingField;
```

- `private Game.Prefabs.TransportType <requireStops>k__BackingField`  

```csharp
private Game.Prefabs.TransportType <requireStops>k__BackingField;
```

- `private Game.Net.Layer <requireNet>k__BackingField`  

```csharp
private Game.Net.Layer <requireNet>k__BackingField;
```

- `private Game.Prefabs.InfoviewPrefab <infoview>k__BackingField`  

```csharp
private Game.Prefabs.InfoviewPrefab <infoview>k__BackingField;
```

- `private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> <infomodes>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> <infomodes>k__BackingField;
```

- `private Game.Tools.Snap <selectedSnap>k__BackingField`  

```csharp
private Game.Tools.Snap <selectedSnap>k__BackingField;
```

- `private Game.Tools.ApplyMode <applyMode>k__BackingField`  

```csharp
private Game.Tools.ApplyMode <applyMode>k__BackingField;
```

- `private System.Boolean <allowUnderground>k__BackingField`  

```csharp
private System.Boolean <allowUnderground>k__BackingField;
```

- `protected Game.Tools.ToolSystem m_ToolSystem`  

```csharp
protected Game.Tools.ToolSystem m_ToolSystem;
```

- `protected Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
protected Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `protected Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
protected Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `protected Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
protected Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `protected Game.Tools.OriginalDeletedSystem m_OriginalDeletedSystem`  

```csharp
protected Game.Tools.OriginalDeletedSystem m_OriginalDeletedSystem;
```

- `protected Unity.Entities.EntityQuery m_ErrorQuery`  

```csharp
protected Unity.Entities.EntityQuery m_ErrorQuery;
```

- `protected Game.Tools.Snap m_SnapOnMask`  

```csharp
protected Game.Tools.Snap m_SnapOnMask;
```

- `protected Game.Tools.Snap m_SnapOffMask`  

```csharp
protected Game.Tools.Snap m_SnapOffMask;
```

- `protected System.Boolean m_HasFocus`  

```csharp
protected System.Boolean m_HasFocus;
```

- `protected System.Boolean m_FocusChanged`  

```csharp
protected System.Boolean m_FocusChanged;
```

- `protected System.Boolean m_ForceUpdate`  

```csharp
protected System.Boolean m_ForceUpdate;
```

- `private Game.Input.IProxyAction m_ApplyAction`  

```csharp
private Game.Input.IProxyAction m_ApplyAction;
```

- `private Game.Input.IProxyAction m_SecondaryApplyAction`  

```csharp
private Game.Input.IProxyAction m_SecondaryApplyAction;
```

- `private Game.Input.IProxyAction m_CancelAction`  

```csharp
private Game.Input.IProxyAction m_CancelAction;
```

- `private System.Boolean <actionsEnabled>k__BackingField`  

```csharp
private System.Boolean <actionsEnabled>k__BackingField;
```

- `private Game.Tools.ToolBaseSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ToolBaseSystem+TypeHandle __TypeHandle;
```

- `private static System.Action<Game.Input.ProxyAction> EventToolActionPerformed`  

```csharp
private static System.Action<Game.Input.ProxyAction> EventToolActionPerformed;
```

- `public static const Game.Tools.Snap kSnapAllIgnoredMask`  

```csharp
public static const Game.Tools.Snap kSnapAllIgnoredMask;
```


## Properties

- `public System.String toolID { get }`  

```csharp
public System.String toolID { get; }
```

- `public System.Int32 uiModeIndex { get }`  

```csharp
public System.Int32 uiModeIndex { get; }
```

- `public UnityEngine.Color32 color { get; set }`  

```csharp
public UnityEngine.Color32 color { get; set; }
```

- `public Game.Prefabs.BrushPrefab brushType { get; set }`  

```csharp
public Game.Prefabs.BrushPrefab brushType { get; set; }
```

- `public System.Single brushSize { get; set }`  

```csharp
public System.Single brushSize { get; set; }
```

- `public System.Single brushAngle { get; set }`  

```csharp
public System.Single brushAngle { get; set; }
```

- `public System.Single brushStrength { get; set }`  

```csharp
public System.Single brushStrength { get; set; }
```

- `public System.Boolean requireZones { get; protected set }`  

```csharp
public System.Boolean requireZones { get; protected set; }
```

- `public System.Boolean requireUnderground { get; protected set }`  

```csharp
public System.Boolean requireUnderground { get; protected set; }
```

- `public System.Boolean requirePipelines { get; protected set }`  

```csharp
public System.Boolean requirePipelines { get; protected set; }
```

- `public System.Boolean requireNetArrows { get; protected set }`  

```csharp
public System.Boolean requireNetArrows { get; protected set; }
```

- `public System.Boolean requireStopIcons { get; protected set }`  

```csharp
public System.Boolean requireStopIcons { get; protected set; }
```

- `public Game.Areas.AreaTypeMask requireAreas { get; protected set }`  

```csharp
public Game.Areas.AreaTypeMask requireAreas { get; protected set; }
```

- `public Game.Routes.RouteType requireRoutes { get; protected set }`  

```csharp
public Game.Routes.RouteType requireRoutes { get; protected set; }
```

- `public Game.Prefabs.TransportType requireStops { get; protected set }`  

```csharp
public Game.Prefabs.TransportType requireStops { get; protected set; }
```

- `public Game.Net.Layer requireNet { get; protected set }`  

```csharp
public Game.Net.Layer requireNet { get; protected set; }
```

- `public Game.Prefabs.InfoviewPrefab infoview { get; private set }`  

```csharp
public Game.Prefabs.InfoviewPrefab infoview { get; private set; }
```

- `public System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes { get; private set; }
```

- `public Game.Tools.Snap selectedSnap { get; set }`  

```csharp
public Game.Tools.Snap selectedSnap { get; set; }
```

- `public Game.Tools.ApplyMode applyMode { get; protected set }`  

```csharp
public Game.Tools.ApplyMode applyMode { get; protected set; }
```

- `public System.Boolean allowUnderground { get; protected set }`  

```csharp
public System.Boolean allowUnderground { get; protected set; }
```

- `public System.Boolean brushing { get }`  

```csharp
public System.Boolean brushing { get; }
```

- `protected Game.Input.IProxyAction applyAction { protected get }`  

```csharp
protected Game.Input.IProxyAction applyAction { protected get; }
```

- `protected Game.Input.IProxyAction secondaryApplyAction { protected get }`  

```csharp
protected Game.Input.IProxyAction secondaryApplyAction { protected get; }
```

- `protected Game.Input.IProxyAction cancelAction { protected get }`  

```csharp
protected Game.Input.IProxyAction cancelAction { protected get; }
```

- `protected Game.Input.IProxyAction applyActionOverride { protected get; protected set }`  

```csharp
protected Game.Input.IProxyAction applyActionOverride { protected get; protected set; }
```

- `protected Game.Input.IProxyAction secondaryApplyActionOverride { protected get; protected set }`  

```csharp
protected Game.Input.IProxyAction secondaryApplyActionOverride { protected get; protected set; }
```

- `protected Game.Input.IProxyAction cancelActionOverride { protected get; protected set }`  

```csharp
protected Game.Input.IProxyAction cancelActionOverride { protected get; protected set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> baseToolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> baseToolActions { private get; }
```

- `internal System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> actions { internal get }`  

```csharp
internal System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> actions { internal get; }
```

- `private System.Boolean actionsEnabled { private get; private set }`  

```csharp
private System.Boolean actionsEnabled { private get; private set; }
```


## Constructors

- `protected ToolBaseSystem()`  

```csharp
protected ToolBaseSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected DestroyDefinitions(Unity.Entities.EntityQuery group, Game.Tools.ToolOutputBarrier barrier, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected Unity.Jobs.JobHandle DestroyDefinitions(Unity.Entities.EntityQuery group, Game.Tools.ToolOutputBarrier barrier, Unity.Jobs.JobHandle inputDeps);
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

- `protected EnsureCachedBrushData() : System.Void`  

```csharp
protected System.Void EnsureCachedBrushData();
```

- `public Equals(Game.Tools.ToolBaseSystem other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Tools.ToolBaseSystem other);
```

- `protected FindDefaultBrush(Unity.Entities.EntityQuery query) : Game.Prefabs.BrushPrefab`  

```csharp
protected Game.Prefabs.BrushPrefab FindDefaultBrush(Unity.Entities.EntityQuery query);
```

- `public static GetActualSnap(Game.Tools.Snap selectedSnap, Game.Tools.Snap onMask, Game.Tools.Snap offMask) : Game.Tools.Snap`  

```csharp
public static Game.Tools.Snap GetActualSnap(Game.Tools.Snap selectedSnap, Game.Tools.Snap onMask, Game.Tools.Snap offMask);
```

- `protected GetActualSnap() : Game.Tools.Snap`  

```csharp
protected Game.Tools.Snap GetActualSnap();
```

- `protected virtual GetAllowApply() : System.Boolean`  

```csharp
protected virtual System.Boolean GetAllowApply();
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `protected GetBrushQuery() : Unity.Entities.EntityQuery`  

```csharp
protected Unity.Entities.EntityQuery GetBrushQuery();
```

- `protected GetContainerQuery() : Unity.Entities.EntityQuery`  

```csharp
protected Unity.Entities.EntityQuery GetContainerQuery();
```

- `protected GetContainers(Unity.Entities.EntityQuery group, Unity.Entities.Entity& laneContainer, Unity.Entities.Entity& transformContainer) : System.Boolean`  

```csharp
protected System.Boolean GetContainers(Unity.Entities.EntityQuery group, Unity.Entities.Entity& laneContainer, Unity.Entities.Entity& transformContainer);
```

- `protected GetDefinitionQuery() : Unity.Entities.EntityQuery`  

```csharp
protected Unity.Entities.EntityQuery GetDefinitionQuery();
```

- `public abstract GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public abstract Game.Prefabs.PrefabBase GetPrefab();
```

- `protected GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
protected System.Boolean GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit);
```

- `protected GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected System.Boolean GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit, System.Boolean& forceUpdate);
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public virtual System.Void InitializeRaycast();
```

- `protected InvertBrushes(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected Unity.Jobs.JobHandle InvertBrushes(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
```

- `private OnActionInteraction(Game.Input.ProxyAction action, UnityEngine.InputSystem.InputActionPhase phase) : System.Void`  

```csharp
private System.Void OnActionInteraction(Game.Input.ProxyAction action, UnityEngine.InputSystem.InputActionPhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnFocusChanged(System.Boolean hasfocus) : System.Void`  

```csharp
protected virtual System.Void OnFocusChanged(System.Boolean hasfocus);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected OnUpdate() : System.Void`  

```csharp
protected System.Void OnUpdate();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `private virtual ResetActions() : System.Void`  

```csharp
private virtual System.Void ResetActions();
```

- `protected SetAction(Game.Input.IProxyAction& action, Game.Input.IProxyAction newAction) : System.Void`  

```csharp
protected System.Void SetAction(Game.Input.IProxyAction& action, Game.Input.IProxyAction newAction);
```

- `private virtual SetActions() : System.Void`  

```csharp
private virtual System.Void SetActions();
```

- `private SetInteraction(System.Boolean set) : System.Void`  

```csharp
private System.Void SetInteraction(System.Boolean set);
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public virtual System.Void SetUnderground(System.Boolean underground);
```

- `public ToggleToolOptions(System.Boolean enabled) : System.Void`  

```csharp
public System.Void ToggleToolOptions(System.Boolean enabled);
```

- `public abstract TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public abstract System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private virtual System.Void UpdateActions();
```

- `protected UpdateInfoview(Unity.Entities.Entity prefab) : System.Void`  

```csharp
protected System.Void UpdateInfoview(Unity.Entities.Entity prefab);
```


## Events

- `EventToolActionPerformed` : `System.Action<Game.Input.ProxyAction>`  

```csharp
public event System.Action<Game.Input.ProxyAction> EventToolActionPerformed;
```


## Nested types

- `Game.Tools.ToolBaseSystem+DestroyDefinitionsJob`  
- `Game.Tools.ToolBaseSystem+InvertBrushesJob`  
- `Game.Tools.ToolBaseSystem+TypeHandle`  
- `Game.Tools.ToolBaseSystem+<get_baseToolActions>d__124`  
- `Game.Tools.ToolBaseSystem+<get_toolActions>d__122`  

