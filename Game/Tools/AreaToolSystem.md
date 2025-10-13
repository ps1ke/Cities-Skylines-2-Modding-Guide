# Game.Tools.AreaToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.AreaToolSystem+Mode <mode>k__BackingField;
    private Unity.Entities.Entity <recreate>k__BackingField;
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <allowGenerate>k__BackingField;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Input.IProxyAction m_AddAreaNode;
    private Game.Input.IProxyAction m_InsertAreaNode;
    private Game.Input.IProxyAction m_MergeAreaNode;
    private Game.Input.IProxyAction m_MoveAreaNode;
    private Game.Input.IProxyAction m_DeleteAreaNode;
    private Game.Input.IProxyAction m_UndoAreaNode;
    private Game.Input.IProxyAction m_CompleteArea;
    private Game.Input.IProxyAction m_CreateArea;
    private Game.Input.IProxyAction m_DeleteArea;
    private Game.Input.IProxyAction m_DiscardInsertAreaNode;
    private Game.Input.IProxyAction m_DiscardMoveAreaNode;
    private Game.Input.IProxyAction m_DiscardMergeAreaNode;
    private Game.Input.IProxyAction m_CreateAreaOrMoveAreaNode;
    private Game.Input.IProxyAction m_CreateAreaOrInsertAreaNode;
    private System.Boolean m_ApplyBlocked;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_TempAreaQuery;
    private Unity.Entities.EntityQuery m_TempBuildingQuery;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_MoveStartPositions;
    private Colossal.Collections.NativeValue<Game.Tools.AreaToolSystem+Tooltip> m_Tooltip;
    private Game.Tools.AreaToolSystem+Mode m_LastMode;
    private Game.Tools.AreaToolSystem+State m_State;
    private Game.Prefabs.AreaPrefab m_Prefab;
    private System.Boolean m_ControlPointsMoved;
    private System.Boolean m_AllowCreateArea;
    private System.Boolean m_ForceCancel;
    private Game.Tools.AreaToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public Game.Tools.AreaToolSystem+Mode mode { get; set; }
    public Game.Tools.AreaToolSystem+Mode actualMode { get; }
    public Unity.Entities.Entity recreate { get; set; }
    public System.Boolean underground { get; set; }
    public System.Boolean allowGenerate { get; private set; }
    public Game.Tools.AreaToolSystem+State state { get; }
    public Game.Tools.AreaToolSystem+Tooltip tooltip { get; }
    public Game.Prefabs.AreaPrefab prefab { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public AreaToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    private static System.Void GetAvailableSnapMask(Game.Prefabs.AreaGeometryData prefabAreaData, System.Boolean editorMode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Collections.NativeList`1[[Game.Tools.ControlPoint, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& moveStartPositions, Unity.Jobs.JobHandle& dependencies);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private System.Void UpdateApplyAction();
    private System.Void UpdateCancelAction();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempBuildings);
    private System.Void UpdateSecondaryApplyAction();
}
```


## Fields

- `private Game.Tools.AreaToolSystem+Mode <mode>k__BackingField`  

```csharp
private Game.Tools.AreaToolSystem+Mode <mode>k__BackingField;
```

- `private Unity.Entities.Entity <recreate>k__BackingField`  

```csharp
private Unity.Entities.Entity <recreate>k__BackingField;
```

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <allowGenerate>k__BackingField`  

```csharp
private System.Boolean <allowGenerate>k__BackingField;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Input.IProxyAction m_AddAreaNode`  

```csharp
private Game.Input.IProxyAction m_AddAreaNode;
```

- `private Game.Input.IProxyAction m_InsertAreaNode`  

```csharp
private Game.Input.IProxyAction m_InsertAreaNode;
```

- `private Game.Input.IProxyAction m_MergeAreaNode`  

```csharp
private Game.Input.IProxyAction m_MergeAreaNode;
```

- `private Game.Input.IProxyAction m_MoveAreaNode`  

```csharp
private Game.Input.IProxyAction m_MoveAreaNode;
```

- `private Game.Input.IProxyAction m_DeleteAreaNode`  

```csharp
private Game.Input.IProxyAction m_DeleteAreaNode;
```

- `private Game.Input.IProxyAction m_UndoAreaNode`  

```csharp
private Game.Input.IProxyAction m_UndoAreaNode;
```

- `private Game.Input.IProxyAction m_CompleteArea`  

```csharp
private Game.Input.IProxyAction m_CompleteArea;
```

- `private Game.Input.IProxyAction m_CreateArea`  

```csharp
private Game.Input.IProxyAction m_CreateArea;
```

- `private Game.Input.IProxyAction m_DeleteArea`  

```csharp
private Game.Input.IProxyAction m_DeleteArea;
```

- `private Game.Input.IProxyAction m_DiscardInsertAreaNode`  

```csharp
private Game.Input.IProxyAction m_DiscardInsertAreaNode;
```

- `private Game.Input.IProxyAction m_DiscardMoveAreaNode`  

```csharp
private Game.Input.IProxyAction m_DiscardMoveAreaNode;
```

- `private Game.Input.IProxyAction m_DiscardMergeAreaNode`  

```csharp
private Game.Input.IProxyAction m_DiscardMergeAreaNode;
```

- `private Game.Input.IProxyAction m_CreateAreaOrMoveAreaNode`  

```csharp
private Game.Input.IProxyAction m_CreateAreaOrMoveAreaNode;
```

- `private Game.Input.IProxyAction m_CreateAreaOrInsertAreaNode`  

```csharp
private Game.Input.IProxyAction m_CreateAreaOrInsertAreaNode;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_TempAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempAreaQuery;
```

- `private Unity.Entities.EntityQuery m_TempBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_MoveStartPositions`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_MoveStartPositions;
```

- `private Colossal.Collections.NativeValue<Game.Tools.AreaToolSystem+Tooltip> m_Tooltip`  

```csharp
private Colossal.Collections.NativeValue<Game.Tools.AreaToolSystem+Tooltip> m_Tooltip;
```

- `private Game.Tools.AreaToolSystem+Mode m_LastMode`  

```csharp
private Game.Tools.AreaToolSystem+Mode m_LastMode;
```

- `private Game.Tools.AreaToolSystem+State m_State`  

```csharp
private Game.Tools.AreaToolSystem+State m_State;
```

- `private Game.Prefabs.AreaPrefab m_Prefab`  

```csharp
private Game.Prefabs.AreaPrefab m_Prefab;
```

- `private System.Boolean m_ControlPointsMoved`  

```csharp
private System.Boolean m_ControlPointsMoved;
```

- `private System.Boolean m_AllowCreateArea`  

```csharp
private System.Boolean m_AllowCreateArea;
```

- `private System.Boolean m_ForceCancel`  

```csharp
private System.Boolean m_ForceCancel;
```

- `private Game.Tools.AreaToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.AreaToolSystem+TypeHandle __TypeHandle;
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

- `public Game.Tools.AreaToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.AreaToolSystem+Mode mode { get; set; }
```

- `public Game.Tools.AreaToolSystem+Mode actualMode { get }`  

```csharp
public Game.Tools.AreaToolSystem+Mode actualMode { get; }
```

- `public Unity.Entities.Entity recreate { get; set }`  

```csharp
public Unity.Entities.Entity recreate { get; set; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean allowGenerate { get; private set }`  

```csharp
public System.Boolean allowGenerate { get; private set; }
```

- `public Game.Tools.AreaToolSystem+State state { get }`  

```csharp
public Game.Tools.AreaToolSystem+State state { get; }
```

- `public Game.Tools.AreaToolSystem+Tooltip tooltip { get }`  

```csharp
public Game.Tools.AreaToolSystem+Tooltip tooltip { get; }
```

- `public Game.Prefabs.AreaPrefab prefab { get; set }`  

```csharp
public Game.Prefabs.AreaPrefab prefab { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public AreaToolSystem()`  

```csharp
public AreaToolSystem();
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

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `private static GetAvailableSnapMask(Game.Prefabs.AreaGeometryData prefabAreaData, System.Boolean editorMode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static System.Void GetAvailableSnapMask(Game.Prefabs.AreaGeometryData prefabAreaData, System.Boolean editorMode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `public GetControlPoints(Unity.Collections.NativeList`1[[Game.Tools.ControlPoint, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& moveStartPositions, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  

```csharp
public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Collections.NativeList`1[[Game.Tools.ControlPoint, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& moveStartPositions, Unity.Jobs.JobHandle& dependencies);
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public virtual System.Void SetUnderground(System.Boolean underground);
```

- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas);
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

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempBuildings) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempBuildings);
```

- `private UpdateSecondaryApplyAction() : System.Void`  

```csharp
private System.Void UpdateSecondaryApplyAction();
```


## Nested types

- `Game.Tools.AreaToolSystem+Mode`  
- `Game.Tools.AreaToolSystem+State`  
- `Game.Tools.AreaToolSystem+Tooltip`  
- `Game.Tools.AreaToolSystem+SnapJob`  
- `Game.Tools.AreaToolSystem+RemoveMapTilesJob`  
- `Game.Tools.AreaToolSystem+CreateDefinitionsJob`  
- `Game.Tools.AreaToolSystem+TypeHandle`  
- `Game.Tools.AreaToolSystem+<get_toolActions>d__56`  

