# Game.Tools.ObjectToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ObjectToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectToolSystem : Game.Tools.ObjectToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.ObjectToolSystem+Mode <mode>k__BackingField;
    private Game.Tools.AgeMask <ageMask>k__BackingField;
    private Game.Tools.Snap m_SelectedSnap;
    private System.Single m_Distance;
    private System.Single <distanceScale>k__BackingField;
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <allowCreate>k__BackingField;
    private System.Boolean <allowLine>k__BackingField;
    private System.Boolean <allowCurve>k__BackingField;
    private System.Boolean <allowBrush>k__BackingField;
    private System.Boolean <allowStamp>k__BackingField;
    private System.Boolean <allowAge>k__BackingField;
    private System.Boolean <allowRotation>k__BackingField;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_ContainerQuery;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Unity.Entities.EntityQuery m_LotQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_VisibleQuery;
    private Game.Input.IProxyAction m_EraseObject;
    private Game.Input.IProxyAction m_MoveObject;
    private Game.Input.IProxyAction m_PaintObject;
    private Game.Input.IProxyAction m_PlaceObject;
    private Game.Input.IProxyAction m_PlaceUpgrade;
    private Game.Input.IProxyAction m_PreciseRotation;
    private Game.Input.IProxyAction m_RotateObject;
    private Game.Input.IProxyAction m_PlaceNetEdge;
    private Game.Input.IProxyAction m_PlaceNetControlPoint;
    private Game.Input.IProxyAction m_UndoNetControlPoint;
    private Game.Input.IProxyAction m_DowngradeNetEdge;
    private Game.Input.IProxyAction m_UpgradeNetEdge;
    private Game.Input.IProxyAction m_DiscardUpgrade;
    private Game.Input.IProxyAction m_DiscardDowngrade;
    private Game.Input.IProxyAction m_ReplaceNetEdge;
    private System.Boolean m_ApplyBlocked;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Unity.Collections.NativeList<Game.Tools.SubSnapPoint> m_SubSnapPoints;
    private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates;
    private Unity.Collections.NativeReference<Game.Tools.ObjectToolSystem+Rotation> m_Rotation;
    private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Game.Tools.ControlPoint m_StartPoint;
    private Unity.Entities.Entity m_UpgradingObject;
    private Unity.Entities.Entity m_MovingObject;
    private Unity.Entities.Entity m_MovingInitialized;
    private Game.Tools.ObjectToolSystem+State m_State;
    private Game.Tools.ObjectToolSystem+Mode m_LastActualMode;
    private System.Boolean m_RotationModified;
    private System.Boolean m_ForceCancel;
    private Unity.Mathematics.float3 m_RotationStartPosition;
    private Unity.Mathematics.quaternion m_StartRotation;
    private System.Single m_StartCameraAngle;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Common.RandomSeed m_RandomSeed;
    private Game.Prefabs.ObjectPrefab m_Prefab;
    private Game.Prefabs.ObjectPrefab m_SelectedPrefab;
    private Game.Prefabs.TransformPrefab m_TransformPrefab;
    private Game.CameraController m_CameraController;
    private Game.Tools.ObjectToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;
    private static const System.String kTree;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public Game.Tools.ObjectToolSystem+Mode mode { get; set; }
    public Game.Tools.ObjectToolSystem+Mode actualMode { get; }
    public System.Boolean isUpgradeMode { get; }
    public Game.Tools.AgeMask ageMask { get; set; }
    public Game.Tools.AgeMask actualAgeMask { get; }
    public Game.Prefabs.ObjectPrefab prefab { get; set; }
    public Game.Prefabs.TransformPrefab transform { get; set; }
    public Game.Tools.Snap selectedSnap { get; set; }
    public System.Single distance { get; set; }
    public System.Single distanceScale { get; private set; }
    public System.Boolean underground { get; set; }
    public System.Boolean allowCreate { get; private set; }
    public System.Boolean allowLine { get; private set; }
    public System.Boolean allowCurve { get; private set; }
    public System.Boolean allowBrush { get; private set; }
    public System.Boolean allowStamp { get; private set; }
    public System.Boolean allowAge { get; private set; }
    public System.Boolean allowRotation { get; private set; }
    public System.Boolean brushing { get; }
    public Game.Tools.ObjectToolSystem+State state { get; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
    private System.Single cameraAngle { private get; }

    public ObjectToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    internal static System.Boolean <GetAllowDowngrade>g__Condition|143_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement);
    private System.Boolean <GetAllowUpgrade>g__Condition|142_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    private Unity.Jobs.JobHandle FixNetControlPoints(Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Boolean GetAllowApply();
    protected System.Boolean GetAllowDowngrade(System.Boolean& replacementExist);
    protected System.Boolean GetAllowPreciseRotation();
    protected System.Boolean GetAllowRotation();
    protected System.Boolean GetAllowUpgrade(System.Boolean& replacementExist);
    protected System.Boolean GetAllowUpgradeOrDowngrade(System.Func<Game.Tools.NetToolSystem+UpgradeState, Game.Net.SubReplacement, System.Boolean> condition, Game.Tools.ObjectToolSystem+State mode, System.Boolean& replacementExist);
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    private static System.Void GetAvailableSnapMask(Game.Prefabs.PlaceableObjectData prefabPlaceableData, System.Boolean editorMode, System.Boolean isBuilding, System.Boolean isAssetStamp, Game.Tools.ObjectToolSystem+Mode mode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Jobs.JobHandle& dependencies);
    private static System.Int32 GetMaxControlPointCount(Game.Tools.ObjectToolSystem+Mode mode);
    public Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> GetNetUpgradeStates(Unity.Jobs.JobHandle& dependencies);
    private Game.Prefabs.ObjectPrefab GetObjectPrefab();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public Unity.Collections.NativeList<Game.Tools.SubSnapPoint> GetSubSnapPoints(Unity.Jobs.JobHandle& dependencies);
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    private System.Boolean HaveBrushSettingsChanged();
    public virtual System.Void InitializeRaycast();
    private System.Void InitializeRotation(Unity.Entities.Entity entity, Game.Prefabs.PlaceableObjectData placeableObjectData);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private System.Void Randomize();
    private virtual System.Void ResetActions();
    private System.Void Rotate(System.Single angle, System.Boolean fromStart, System.Boolean align);
    private System.Void SetAppliedUpgrade(System.Boolean removing);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoint(Unity.Jobs.JobHandle inputDeps);
    public System.Void StartMoving(Unity.Entities.Entity movingObject);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle UpdateSubReplacementDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.ObjectToolSystem+Mode <mode>k__BackingField`  

```csharp
private Game.Tools.ObjectToolSystem+Mode <mode>k__BackingField;
```

- `private Game.Tools.AgeMask <ageMask>k__BackingField`  

```csharp
private Game.Tools.AgeMask <ageMask>k__BackingField;
```

- `private Game.Tools.Snap m_SelectedSnap`  

```csharp
private Game.Tools.Snap m_SelectedSnap;
```

- `private System.Single m_Distance`  

```csharp
private System.Single m_Distance;
```

- `private System.Single <distanceScale>k__BackingField`  

```csharp
private System.Single <distanceScale>k__BackingField;
```

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <allowCreate>k__BackingField`  

```csharp
private System.Boolean <allowCreate>k__BackingField;
```

- `private System.Boolean <allowLine>k__BackingField`  

```csharp
private System.Boolean <allowLine>k__BackingField;
```

- `private System.Boolean <allowCurve>k__BackingField`  

```csharp
private System.Boolean <allowCurve>k__BackingField;
```

- `private System.Boolean <allowBrush>k__BackingField`  

```csharp
private System.Boolean <allowBrush>k__BackingField;
```

- `private System.Boolean <allowStamp>k__BackingField`  

```csharp
private System.Boolean <allowStamp>k__BackingField;
```

- `private System.Boolean <allowAge>k__BackingField`  

```csharp
private System.Boolean <allowAge>k__BackingField;
```

- `private System.Boolean <allowRotation>k__BackingField`  

```csharp
private System.Boolean <allowRotation>k__BackingField;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_ContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContainerQuery;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Unity.Entities.EntityQuery m_LotQuery`  

```csharp
private Unity.Entities.EntityQuery m_LotQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_VisibleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VisibleQuery;
```

- `private Game.Input.IProxyAction m_EraseObject`  

```csharp
private Game.Input.IProxyAction m_EraseObject;
```

- `private Game.Input.IProxyAction m_MoveObject`  

```csharp
private Game.Input.IProxyAction m_MoveObject;
```

- `private Game.Input.IProxyAction m_PaintObject`  

```csharp
private Game.Input.IProxyAction m_PaintObject;
```

- `private Game.Input.IProxyAction m_PlaceObject`  

```csharp
private Game.Input.IProxyAction m_PlaceObject;
```

- `private Game.Input.IProxyAction m_PlaceUpgrade`  

```csharp
private Game.Input.IProxyAction m_PlaceUpgrade;
```

- `private Game.Input.IProxyAction m_PreciseRotation`  

```csharp
private Game.Input.IProxyAction m_PreciseRotation;
```

- `private Game.Input.IProxyAction m_RotateObject`  

```csharp
private Game.Input.IProxyAction m_RotateObject;
```

- `private Game.Input.IProxyAction m_PlaceNetEdge`  

```csharp
private Game.Input.IProxyAction m_PlaceNetEdge;
```

- `private Game.Input.IProxyAction m_PlaceNetControlPoint`  

```csharp
private Game.Input.IProxyAction m_PlaceNetControlPoint;
```

- `private Game.Input.IProxyAction m_UndoNetControlPoint`  

```csharp
private Game.Input.IProxyAction m_UndoNetControlPoint;
```

- `private Game.Input.IProxyAction m_DowngradeNetEdge`  

```csharp
private Game.Input.IProxyAction m_DowngradeNetEdge;
```

- `private Game.Input.IProxyAction m_UpgradeNetEdge`  

```csharp
private Game.Input.IProxyAction m_UpgradeNetEdge;
```

- `private Game.Input.IProxyAction m_DiscardUpgrade`  

```csharp
private Game.Input.IProxyAction m_DiscardUpgrade;
```

- `private Game.Input.IProxyAction m_DiscardDowngrade`  

```csharp
private Game.Input.IProxyAction m_DiscardDowngrade;
```

- `private Game.Input.IProxyAction m_ReplaceNetEdge`  

```csharp
private Game.Input.IProxyAction m_ReplaceNetEdge;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Unity.Collections.NativeList<Game.Tools.SubSnapPoint> m_SubSnapPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.SubSnapPoint> m_SubSnapPoints;
```

- `private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates`  

```csharp
private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates;
```

- `private Unity.Collections.NativeReference<Game.Tools.ObjectToolSystem+Rotation> m_Rotation`  

```csharp
private Unity.Collections.NativeReference<Game.Tools.ObjectToolSystem+Rotation> m_Rotation;
```

- `private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade`  

```csharp
private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Unity.Entities.Entity m_UpgradingObject`  

```csharp
private Unity.Entities.Entity m_UpgradingObject;
```

- `private Unity.Entities.Entity m_MovingObject`  

```csharp
private Unity.Entities.Entity m_MovingObject;
```

- `private Unity.Entities.Entity m_MovingInitialized`  

```csharp
private Unity.Entities.Entity m_MovingInitialized;
```

- `private Game.Tools.ObjectToolSystem+State m_State`  

```csharp
private Game.Tools.ObjectToolSystem+State m_State;
```

- `private Game.Tools.ObjectToolSystem+Mode m_LastActualMode`  

```csharp
private Game.Tools.ObjectToolSystem+Mode m_LastActualMode;
```

- `private System.Boolean m_RotationModified`  

```csharp
private System.Boolean m_RotationModified;
```

- `private System.Boolean m_ForceCancel`  

```csharp
private System.Boolean m_ForceCancel;
```

- `private Unity.Mathematics.float3 m_RotationStartPosition`  

```csharp
private Unity.Mathematics.float3 m_RotationStartPosition;
```

- `private Unity.Mathematics.quaternion m_StartRotation`  

```csharp
private Unity.Mathematics.quaternion m_StartRotation;
```

- `private System.Single m_StartCameraAngle`  

```csharp
private System.Single m_StartCameraAngle;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Common.RandomSeed m_RandomSeed`  

```csharp
private Game.Common.RandomSeed m_RandomSeed;
```

- `private Game.Prefabs.ObjectPrefab m_Prefab`  

```csharp
private Game.Prefabs.ObjectPrefab m_Prefab;
```

- `private Game.Prefabs.ObjectPrefab m_SelectedPrefab`  

```csharp
private Game.Prefabs.ObjectPrefab m_SelectedPrefab;
```

- `private Game.Prefabs.TransformPrefab m_TransformPrefab`  

```csharp
private Game.Prefabs.TransformPrefab m_TransformPrefab;
```

- `private Game.CameraController m_CameraController`  

```csharp
private Game.CameraController m_CameraController;
```

- `private Game.Tools.ObjectToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ObjectToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```

- `private static const System.String kTree`  

```csharp
private static const System.String kTree;
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

- `public Game.Tools.ObjectToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.ObjectToolSystem+Mode mode { get; set; }
```

- `public Game.Tools.ObjectToolSystem+Mode actualMode { get }`  

```csharp
public Game.Tools.ObjectToolSystem+Mode actualMode { get; }
```

- `public System.Boolean isUpgradeMode { get }`  

```csharp
public System.Boolean isUpgradeMode { get; }
```

- `public Game.Tools.AgeMask ageMask { get; set }`  

```csharp
public Game.Tools.AgeMask ageMask { get; set; }
```

- `public Game.Tools.AgeMask actualAgeMask { get }`  

```csharp
public Game.Tools.AgeMask actualAgeMask { get; }
```

- `public Game.Prefabs.ObjectPrefab prefab { get; set }`  

```csharp
public Game.Prefabs.ObjectPrefab prefab { get; set; }
```

- `public Game.Prefabs.TransformPrefab transform { get; set }`  

```csharp
public Game.Prefabs.TransformPrefab transform { get; set; }
```

- `public Game.Tools.Snap selectedSnap { get; set }`  

```csharp
public Game.Tools.Snap selectedSnap { get; set; }
```

- `public System.Single distance { get; set }`  

```csharp
public System.Single distance { get; set; }
```

- `public System.Single distanceScale { get; private set }`  

```csharp
public System.Single distanceScale { get; private set; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean allowCreate { get; private set }`  

```csharp
public System.Boolean allowCreate { get; private set; }
```

- `public System.Boolean allowLine { get; private set }`  

```csharp
public System.Boolean allowLine { get; private set; }
```

- `public System.Boolean allowCurve { get; private set }`  

```csharp
public System.Boolean allowCurve { get; private set; }
```

- `public System.Boolean allowBrush { get; private set }`  

```csharp
public System.Boolean allowBrush { get; private set; }
```

- `public System.Boolean allowStamp { get; private set }`  

```csharp
public System.Boolean allowStamp { get; private set; }
```

- `public System.Boolean allowAge { get; private set }`  

```csharp
public System.Boolean allowAge { get; private set; }
```

- `public System.Boolean allowRotation { get; private set }`  

```csharp
public System.Boolean allowRotation { get; private set; }
```

- `public System.Boolean brushing { get }`  

```csharp
public System.Boolean brushing { get; }
```

- `public Game.Tools.ObjectToolSystem+State state { get }`  

```csharp
public Game.Tools.ObjectToolSystem+State state { get; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```

- `private System.Single cameraAngle { private get }`  

```csharp
private System.Single cameraAngle { private get; }
```


## Constructors

- `public ObjectToolSystem()`  

```csharp
public ObjectToolSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `internal static <GetAllowDowngrade>g__Condition|143_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement) : System.Boolean`  

```csharp
internal static System.Boolean <GetAllowDowngrade>g__Condition|143_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement);
```

- `private <GetAllowUpgrade>g__Condition|142_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement) : System.Boolean`  

```csharp
private System.Boolean <GetAllowUpgrade>g__Condition|142_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement);
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

- `private FixNetControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle FixNetControlPoints(Unity.Jobs.JobHandle inputDeps);
```

- `protected virtual GetAllowApply() : System.Boolean`  

```csharp
protected virtual System.Boolean GetAllowApply();
```

- `protected GetAllowDowngrade(System.Boolean& replacementExist) : System.Boolean`  

```csharp
protected System.Boolean GetAllowDowngrade(System.Boolean& replacementExist);
```

- `protected GetAllowPreciseRotation() : System.Boolean`  

```csharp
protected System.Boolean GetAllowPreciseRotation();
```

- `protected GetAllowRotation() : System.Boolean`  

```csharp
protected System.Boolean GetAllowRotation();
```

- `protected GetAllowUpgrade(System.Boolean& replacementExist) : System.Boolean`  

```csharp
protected System.Boolean GetAllowUpgrade(System.Boolean& replacementExist);
```

- `protected GetAllowUpgradeOrDowngrade(System.Func<Game.Tools.NetToolSystem+UpgradeState, Game.Net.SubReplacement, System.Boolean> condition, Game.Tools.ObjectToolSystem+State mode, System.Boolean& replacementExist) : System.Boolean`  

```csharp
protected System.Boolean GetAllowUpgradeOrDowngrade(System.Func<Game.Tools.NetToolSystem+UpgradeState, Game.Net.SubReplacement, System.Boolean> condition, Game.Tools.ObjectToolSystem+State mode, System.Boolean& replacementExist);
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `private static GetAvailableSnapMask(Game.Prefabs.PlaceableObjectData prefabPlaceableData, System.Boolean editorMode, System.Boolean isBuilding, System.Boolean isAssetStamp, Game.Tools.ObjectToolSystem+Mode mode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static System.Void GetAvailableSnapMask(Game.Prefabs.PlaceableObjectData prefabPlaceableData, System.Boolean editorMode, System.Boolean isBuilding, System.Boolean isAssetStamp, Game.Tools.ObjectToolSystem+Mode mode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `public GetControlPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  

```csharp
public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Jobs.JobHandle& dependencies);
```

- `private static GetMaxControlPointCount(Game.Tools.ObjectToolSystem+Mode mode) : System.Int32`  

```csharp
private static System.Int32 GetMaxControlPointCount(Game.Tools.ObjectToolSystem+Mode mode);
```

- `public GetNetUpgradeStates(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState>`  

```csharp
public Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> GetNetUpgradeStates(Unity.Jobs.JobHandle& dependencies);
```

- `private GetObjectPrefab() : Game.Prefabs.ObjectPrefab`  

```csharp
private Game.Prefabs.ObjectPrefab GetObjectPrefab();
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public virtual Game.Prefabs.PrefabBase GetPrefab();
```

- `public GetSubSnapPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.SubSnapPoint>`  

```csharp
public Unity.Collections.NativeList<Game.Tools.SubSnapPoint> GetSubSnapPoints(Unity.Jobs.JobHandle& dependencies);
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
```

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
```

- `private HaveBrushSettingsChanged() : System.Boolean`  

```csharp
private System.Boolean HaveBrushSettingsChanged();
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public virtual System.Void InitializeRaycast();
```

- `private InitializeRotation(Unity.Entities.Entity entity, Game.Prefabs.PlaceableObjectData placeableObjectData) : System.Void`  

```csharp
private System.Void InitializeRotation(Unity.Entities.Entity entity, Game.Prefabs.PlaceableObjectData placeableObjectData);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `private Randomize() : System.Void`  

```csharp
private System.Void Randomize();
```

- `private virtual ResetActions() : System.Void`  

```csharp
private virtual System.Void ResetActions();
```

- `private Rotate(System.Single angle, System.Boolean fromStart, System.Boolean align) : System.Void`  

```csharp
private System.Void Rotate(System.Single angle, System.Boolean fromStart, System.Boolean align);
```

- `private SetAppliedUpgrade(System.Boolean removing) : System.Void`  

```csharp
private System.Void SetAppliedUpgrade(System.Boolean removing);
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public virtual System.Void SetUnderground(System.Boolean underground);
```

- `private SnapControlPoint(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle SnapControlPoint(Unity.Jobs.JobHandle inputDeps);
```

- `public StartMoving(Unity.Entities.Entity movingObject) : System.Void`  

```csharp
public System.Void StartMoving(Unity.Entities.Entity movingObject);
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

- `private UpdateSubReplacementDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateSubReplacementDefinitions(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Tools.ObjectToolSystem+Mode`  
- `Game.Tools.ObjectToolSystem+State`  
- `Game.Tools.ObjectToolSystem+Rotation`  
- `Game.Tools.ObjectToolSystem+SnapJob`  
- `Game.Tools.ObjectToolSystem+FindAttachmentBuildingJob`  
- `Game.Tools.ObjectToolSystem+TypeHandle`  
- `Game.Tools.ObjectToolSystem+<get_toolActions>d__106`  

