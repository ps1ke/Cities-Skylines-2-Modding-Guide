# Game.Tools.ObjectToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ObjectToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ObjectToolSystem+Mode <mode>k__BackingField`  
- `private Game.Tools.AgeMask <ageMask>k__BackingField`  
- `private Game.Tools.Snap m_SelectedSnap`  
- `private System.Single m_Distance`  
- `private System.Single <distanceScale>k__BackingField`  
- `private System.Boolean <underground>k__BackingField`  
- `private System.Boolean <allowCreate>k__BackingField`  
- `private System.Boolean <allowLine>k__BackingField`  
- `private System.Boolean <allowCurve>k__BackingField`  
- `private System.Boolean <allowBrush>k__BackingField`  
- `private System.Boolean <allowStamp>k__BackingField`  
- `private System.Boolean <allowAge>k__BackingField`  
- `private System.Boolean <allowRotation>k__BackingField`  
- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_ContainerQuery`  
- `private Unity.Entities.EntityQuery m_BrushQuery`  
- `private Unity.Entities.EntityQuery m_LotQuery`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_VisibleQuery`  
- `private Game.Input.IProxyAction m_EraseObject`  
- `private Game.Input.IProxyAction m_MoveObject`  
- `private Game.Input.IProxyAction m_PaintObject`  
- `private Game.Input.IProxyAction m_PlaceObject`  
- `private Game.Input.IProxyAction m_PlaceUpgrade`  
- `private Game.Input.IProxyAction m_PreciseRotation`  
- `private Game.Input.IProxyAction m_RotateObject`  
- `private Game.Input.IProxyAction m_PlaceNetEdge`  
- `private Game.Input.IProxyAction m_PlaceNetControlPoint`  
- `private Game.Input.IProxyAction m_UndoNetControlPoint`  
- `private Game.Input.IProxyAction m_DowngradeNetEdge`  
- `private Game.Input.IProxyAction m_UpgradeNetEdge`  
- `private Game.Input.IProxyAction m_DiscardUpgrade`  
- `private Game.Input.IProxyAction m_DiscardDowngrade`  
- `private Game.Input.IProxyAction m_ReplaceNetEdge`  
- `private System.Boolean m_ApplyBlocked`  
- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  
- `private Unity.Collections.NativeList<Game.Tools.SubSnapPoint> m_SubSnapPoints`  
- `private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates`  
- `private Unity.Collections.NativeReference<Game.Tools.ObjectToolSystem+Rotation> m_Rotation`  
- `private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade`  
- `private Game.Tools.ControlPoint m_LastRaycastPoint`  
- `private Game.Tools.ControlPoint m_StartPoint`  
- `private Unity.Entities.Entity m_UpgradingObject`  
- `private Unity.Entities.Entity m_MovingObject`  
- `private Unity.Entities.Entity m_MovingInitialized`  
- `private Game.Tools.ObjectToolSystem+State m_State`  
- `private Game.Tools.ObjectToolSystem+Mode m_LastActualMode`  
- `private System.Boolean m_RotationModified`  
- `private System.Boolean m_ForceCancel`  
- `private Unity.Mathematics.float3 m_RotationStartPosition`  
- `private Unity.Mathematics.quaternion m_StartRotation`  
- `private System.Single m_StartCameraAngle`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Game.Common.RandomSeed m_RandomSeed`  
- `private Game.Prefabs.ObjectPrefab m_Prefab`  
- `private Game.Prefabs.ObjectPrefab m_SelectedPrefab`  
- `private Game.Prefabs.TransformPrefab m_TransformPrefab`  
- `private Game.CameraController m_CameraController`  
- `private Game.Tools.ObjectToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  
- `private static const System.String kTree`  

## Properties

- `public System.String toolID { get }`  
- `public System.Int32 uiModeIndex { get }`  
- `public Game.Tools.ObjectToolSystem+Mode mode { get; set }`  
- `public Game.Tools.ObjectToolSystem+Mode actualMode { get }`  
- `public System.Boolean isUpgradeMode { get }`  
- `public Game.Tools.AgeMask ageMask { get; set }`  
- `public Game.Tools.AgeMask actualAgeMask { get }`  
- `public Game.Prefabs.ObjectPrefab prefab { get; set }`  
- `public Game.Prefabs.TransformPrefab transform { get; set }`  
- `public Game.Tools.Snap selectedSnap { get; set }`  
- `public System.Single distance { get; set }`  
- `public System.Single distanceScale { get; private set }`  
- `public System.Boolean underground { get; set }`  
- `public System.Boolean allowCreate { get; private set }`  
- `public System.Boolean allowLine { get; private set }`  
- `public System.Boolean allowCurve { get; private set }`  
- `public System.Boolean allowBrush { get; private set }`  
- `public System.Boolean allowStamp { get; private set }`  
- `public System.Boolean allowAge { get; private set }`  
- `public System.Boolean allowRotation { get; private set }`  
- `public System.Boolean brushing { get }`  
- `public Game.Tools.ObjectToolSystem+State state { get }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  
- `private System.Single cameraAngle { private get }`  

## Constructors

- `public ObjectToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `internal static <GetAllowDowngrade>g__Condition|143_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement) : System.Boolean`  
- `private <GetAllowUpgrade>g__Condition|142_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement) : System.Boolean`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual ElevationDown() : System.Void`  
- `public virtual ElevationScroll() : System.Void`  
- `public virtual ElevationUp() : System.Void`  
- `private FixNetControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `protected virtual GetAllowApply() : System.Boolean`  
- `protected GetAllowDowngrade(System.Boolean& replacementExist) : System.Boolean`  
- `protected GetAllowPreciseRotation() : System.Boolean`  
- `protected GetAllowRotation() : System.Boolean`  
- `protected GetAllowUpgrade(System.Boolean& replacementExist) : System.Boolean`  
- `protected GetAllowUpgradeOrDowngrade(System.Func<Game.Tools.NetToolSystem+UpgradeState, Game.Net.SubReplacement, System.Boolean> condition, Game.Tools.ObjectToolSystem+State mode, System.Boolean& replacementExist) : System.Boolean`  
- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `private static GetAvailableSnapMask(Game.Prefabs.PlaceableObjectData prefabPlaceableData, System.Boolean editorMode, System.Boolean isBuilding, System.Boolean isAssetStamp, Game.Tools.ObjectToolSystem+Mode mode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `public GetControlPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  
- `private static GetMaxControlPointCount(Game.Tools.ObjectToolSystem+Mode mode) : System.Int32`  
- `public GetNetUpgradeStates(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState>`  
- `private GetObjectPrefab() : Game.Prefabs.ObjectPrefab`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `public GetSubSnapPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.SubSnapPoint>`  
- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  
- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  
- `private HaveBrushSettingsChanged() : System.Boolean`  
- `public virtual InitializeRaycast() : System.Void`  
- `private InitializeRotation(Unity.Entities.Entity entity, Game.Prefabs.PlaceableObjectData placeableObjectData) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private Randomize() : System.Void`  
- `private virtual ResetActions() : System.Void`  
- `private Rotate(System.Single angle, System.Boolean fromStart, System.Boolean align) : System.Void`  
- `private SetAppliedUpgrade(System.Boolean removing) : System.Void`  
- `public virtual SetUnderground(System.Boolean underground) : System.Void`  
- `private SnapControlPoint(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public StartMoving(Unity.Entities.Entity movingObject) : System.Void`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private UpdateSubReplacementDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.ObjectToolSystem+Mode`  
- `Game.Tools.ObjectToolSystem+State`  
- `Game.Tools.ObjectToolSystem+Rotation`  
- `Game.Tools.ObjectToolSystem+SnapJob`  
- `Game.Tools.ObjectToolSystem+FindAttachmentBuildingJob`  
- `Game.Tools.ObjectToolSystem+TypeHandle`  
- `Game.Tools.ObjectToolSystem+<get_toolActions>d__106`  

