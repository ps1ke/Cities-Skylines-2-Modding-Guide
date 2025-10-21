# Game.Tools.ZoneToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.ZoneToolSystem+Mode <mode>k__BackingField;
    private Game.Prefabs.ZonePrefab m_Prefab;
    private System.Boolean <overwrite>k__BackingField;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_DefinitionGroup;
    private Unity.Entities.EntityQuery m_TempBlockQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Input.IProxyAction m_ApplyZone;
    private Game.Input.IProxyAction m_RemoveZone;
    private Game.Input.IProxyAction m_DiscardZoning;
    private Game.Input.IProxyAction m_DiscardDezoning;
    private Game.Input.IProxyAction m_DefaultDiscardApply;
    private Game.Input.IProxyAction m_DefaultDiscardRemove;
    private System.Boolean m_ApplyBlocked;
    private Game.Tools.ControlPoint m_RaycastPoint;
    private Game.Tools.ControlPoint m_StartPoint;
    private Colossal.Collections.NativeValue<Game.Tools.ControlPoint> m_SnapPoint;
    private Game.Tools.ZoneToolSystem+State m_State;
    private Game.Tools.ZoneToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public Game.Tools.ZoneToolSystem+Mode mode { get; set; }
    public Game.Prefabs.ZonePrefab prefab { get; set; }
    public System.Boolean overwrite { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public ZoneToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    protected System.Boolean GetAllowApplyZone();
    protected System.Boolean GetAllowRemoveZone();
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle SetZoneType(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle SnapPoint(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.ZoneToolSystem+Mode <mode>k__BackingField`  

```csharp
private Game.Tools.ZoneToolSystem+Mode <mode>k__BackingField;
```

- `private Game.Prefabs.ZonePrefab m_Prefab`  

```csharp
private Game.Prefabs.ZonePrefab m_Prefab;
```

- `private System.Boolean <overwrite>k__BackingField`  

```csharp
private System.Boolean <overwrite>k__BackingField;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionGroup`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionGroup;
```

- `private Unity.Entities.EntityQuery m_TempBlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempBlockQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Input.IProxyAction m_ApplyZone`  

```csharp
private Game.Input.IProxyAction m_ApplyZone;
```

- `private Game.Input.IProxyAction m_RemoveZone`  

```csharp
private Game.Input.IProxyAction m_RemoveZone;
```

- `private Game.Input.IProxyAction m_DiscardZoning`  

```csharp
private Game.Input.IProxyAction m_DiscardZoning;
```

- `private Game.Input.IProxyAction m_DiscardDezoning`  

```csharp
private Game.Input.IProxyAction m_DiscardDezoning;
```

- `private Game.Input.IProxyAction m_DefaultDiscardApply`  

```csharp
private Game.Input.IProxyAction m_DefaultDiscardApply;
```

- `private Game.Input.IProxyAction m_DefaultDiscardRemove`  

```csharp
private Game.Input.IProxyAction m_DefaultDiscardRemove;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Game.Tools.ControlPoint m_RaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_RaycastPoint;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Colossal.Collections.NativeValue<Game.Tools.ControlPoint> m_SnapPoint`  

```csharp
private Colossal.Collections.NativeValue<Game.Tools.ControlPoint> m_SnapPoint;
```

- `private Game.Tools.ZoneToolSystem+State m_State`  

```csharp
private Game.Tools.ZoneToolSystem+State m_State;
```

- `private Game.Tools.ZoneToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ZoneToolSystem+TypeHandle __TypeHandle;
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

- `public System.Int32 uiModeIndex { get }`  

```csharp
public System.Int32 uiModeIndex { get; }
```

- `public Game.Tools.ZoneToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.ZoneToolSystem+Mode mode { get; set; }
```

- `public Game.Prefabs.ZonePrefab prefab { get; set }`  

```csharp
public Game.Prefabs.ZonePrefab prefab { get; set; }
```

- `public System.Boolean overwrite { get; set }`  

```csharp
public System.Boolean overwrite { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public ZoneToolSystem()`  

```csharp
public ZoneToolSystem();
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

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
```

- `protected GetAllowApplyZone() : System.Boolean`  

```csharp
protected System.Boolean GetAllowApplyZone();
```

- `protected GetAllowRemoveZone() : System.Boolean`  

```csharp
protected System.Boolean GetAllowRemoveZone();
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public virtual Game.Prefabs.PrefabBase GetPrefab();
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
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

- `private SetZoneType(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle SetZoneType(Unity.Jobs.JobHandle inputDeps);
```

- `private SnapPoint(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle SnapPoint(Unity.Jobs.JobHandle inputDeps);
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
```

- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private virtual System.Void UpdateActions();
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Tools.ZoneToolSystem+Mode`  
- `Game.Tools.ZoneToolSystem+State`  
- `Game.Tools.ZoneToolSystem+SetZoneTypeJob`  
- `Game.Tools.ZoneToolSystem+SnapJob`  
- `Game.Tools.ZoneToolSystem+CreateDefinitionsJob`  
- `Game.Tools.ZoneToolSystem+TypeHandle`  
- `Game.Tools.ZoneToolSystem+<get_toolActions>d__34`  

