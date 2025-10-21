# Game.Tools.BulldozeToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BulldozeToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.BulldozeToolSystem+Mode <mode>k__BackingField;
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <allowManipulation>k__BackingField;
    private System.Boolean <debugBypassBulldozeConfirmation>k__BackingField;
    private Game.Prefabs.BulldozePrefab <prefab>k__BackingField;
    public System.Action EventConfirmationRequested;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_RoadQuery;
    private Unity.Entities.EntityQuery m_PlantQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Game.Tools.BulldozeToolSystem+State m_State;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Game.Input.IProxyAction m_Bulldoze;
    private Game.Input.IProxyAction m_BulldozeDiscard;
    private System.Boolean m_ApplyBlocked;
    private Game.Tools.BulldozeToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public System.Boolean allowUnderground { get; }
    public Game.Tools.BulldozeToolSystem+Mode mode { get; set; }
    public Game.Tools.BulldozeToolSystem+Mode actualMode { get; }
    public System.Boolean underground { get; set; }
    public System.Boolean allowManipulation { get; set; }
    public System.Boolean debugBypassBulldozeConfirmation { get; set; }
    public Game.Prefabs.BulldozePrefab prefab { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public BulldozeToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps);
    public System.Void ConfirmAction(System.Boolean confirm);
    private System.Boolean ConfirmationNeeded();
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    public virtual System.Void InitializeRaycast();
    private System.Boolean IsMultiSelection();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.BulldozeToolSystem+Mode <mode>k__BackingField`  

```csharp
private Game.Tools.BulldozeToolSystem+Mode <mode>k__BackingField;
```

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <allowManipulation>k__BackingField`  

```csharp
private System.Boolean <allowManipulation>k__BackingField;
```

- `private System.Boolean <debugBypassBulldozeConfirmation>k__BackingField`  

```csharp
private System.Boolean <debugBypassBulldozeConfirmation>k__BackingField;
```

- `private Game.Prefabs.BulldozePrefab <prefab>k__BackingField`  

```csharp
private Game.Prefabs.BulldozePrefab <prefab>k__BackingField;
```

- `public System.Action EventConfirmationRequested`  

```csharp
public System.Action EventConfirmationRequested;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  

```csharp
private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_RoadQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadQuery;
```

- `private Unity.Entities.EntityQuery m_PlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlantQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Game.Tools.BulldozeToolSystem+State m_State`  

```csharp
private Game.Tools.BulldozeToolSystem+State m_State;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Game.Input.IProxyAction m_Bulldoze`  

```csharp
private Game.Input.IProxyAction m_Bulldoze;
```

- `private Game.Input.IProxyAction m_BulldozeDiscard`  

```csharp
private Game.Input.IProxyAction m_BulldozeDiscard;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Game.Tools.BulldozeToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.BulldozeToolSystem+TypeHandle __TypeHandle;
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

- `public System.Boolean allowUnderground { get }`  

```csharp
public System.Boolean allowUnderground { get; }
```

- `public Game.Tools.BulldozeToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.BulldozeToolSystem+Mode mode { get; set; }
```

- `public Game.Tools.BulldozeToolSystem+Mode actualMode { get }`  

```csharp
public Game.Tools.BulldozeToolSystem+Mode actualMode { get; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean allowManipulation { get; set }`  

```csharp
public System.Boolean allowManipulation { get; set; }
```

- `public System.Boolean debugBypassBulldozeConfirmation { get; set }`  

```csharp
public System.Boolean debugBypassBulldozeConfirmation { get; set; }
```

- `public Game.Prefabs.BulldozePrefab prefab { get; set }`  

```csharp
public Game.Prefabs.BulldozePrefab prefab { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public BulldozeToolSystem()`  

```csharp
public BulldozeToolSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private Apply(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps);
```

- `public ConfirmAction(System.Boolean confirm) : System.Void`  

```csharp
public System.Void ConfirmAction(System.Boolean confirm);
```

- `private ConfirmationNeeded() : System.Boolean`  

```csharp
private System.Boolean ConfirmationNeeded();
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

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public virtual System.Void InitializeRaycast();
```

- `private IsMultiSelection() : System.Boolean`  

```csharp
private System.Boolean IsMultiSelection();
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

- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps);
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

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Tools.BulldozeToolSystem+Mode`  
- `Game.Tools.BulldozeToolSystem+State`  
- `Game.Tools.BulldozeToolSystem+PathEdge`  
- `Game.Tools.BulldozeToolSystem+PathItem`  
- `Game.Tools.BulldozeToolSystem+SnapJob`  
- `Game.Tools.BulldozeToolSystem+CreateDefinitionsJob`  
- `Game.Tools.BulldozeToolSystem+TypeHandle`  
- `Game.Tools.BulldozeToolSystem+<get_toolActions>d__47`  

