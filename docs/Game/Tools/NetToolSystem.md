# Game.Tools.NetToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean m_LoadingPreferences`  
- `private Game.Tools.NetToolSystem+Mode m_Mode`  
- `private System.Single m_Elevation`  
- `private System.Single m_LastMouseElevation`  
- `private System.Single m_ElevationStep`  
- `private System.Int32 m_ParallelCount`  
- `private System.Single m_ParallelOffset`  
- `private System.Boolean m_Underground`  
- `private Game.Tools.Snap m_SelectedSnap`  
- `private System.Boolean <upgradeOnly>k__BackingField`  
- `private System.Boolean <allowParallel>k__BackingField`  
- `private System.Boolean <allowGrid>k__BackingField`  
- `private System.Boolean <allowReplace>k__BackingField`  
- `private System.Boolean <serviceUpgrade>k__BackingField`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Prefabs.NetInitializeSystem m_NetInitializeSystem`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_EdgeQuery`  
- `private Unity.Entities.EntityQuery m_NodeQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Unity.Entities.EntityQuery m_ContainerQuery`  
- `private Game.Input.IProxyAction m_DowngradeNetEdge`  
- `private Game.Input.IProxyAction m_PlaceNetControlPoint`  
- `private Game.Input.IProxyAction m_PlaceNetEdge`  
- `private Game.Input.IProxyAction m_PlaceNetNode`  
- `private Game.Input.IProxyAction m_ReplaceNetEdge`  
- `private Game.Input.IProxyAction m_UndoNetControlPoint`  
- `private Game.Input.IProxyAction m_UpgradeNetEdge`  
- `private Game.Input.IProxyAction m_DiscardUpgrade`  
- `private Game.Input.IProxyAction m_DiscardDowngrade`  
- `private Game.Input.IProxyAction m_DiscardReplace`  
- `private System.Boolean m_ApplyBlocked`  
- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  
- `private Unity.Collections.NativeList<Game.Tools.SnapLine> m_SnapLines`  
- `private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates`  
- `private Unity.Collections.NativeReference<Unity.Entities.Entity> m_StartEntity`  
- `private Unity.Collections.NativeReference<Unity.Entities.Entity> m_LastSnappedEntity`  
- `private Unity.Collections.NativeReference<System.Int32> m_LastControlPointsAngle`  
- `private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade`  
- `private Game.Tools.ControlPoint m_LastRaycastPoint`  
- `private Game.Tools.ControlPoint m_ApplyStartPoint`  
- `private Game.Tools.NetToolSystem+State m_State`  
- `private Colossal.Mathematics.Bounds1 m_LastElevationRange`  
- `private Game.Tools.NetToolSystem+Mode m_LastActualMode`  
- `private System.Single m_ApplyTimer`  
- `private Game.Prefabs.NetPrefab m_Prefab`  
- `private Game.Prefabs.NetPrefab m_SelectedPrefab`  
- `private Game.Prefabs.NetLanePrefab m_LanePrefab`  
- `private System.Boolean m_AllowUndergroundReplace`  
- `private System.Boolean m_ForceCancel`  
- `private Game.Common.RandomSeed m_RandomSeed`  
- `private Game.Tools.NetToolSystem+NetToolPreferences m_DefaultToolPreferences`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Tools.NetToolSystem+NetToolPreferences> m_ToolPreferences`  
- `private Game.Tools.NetToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public System.Int32 uiModeIndex { get }`  
- `public Game.Tools.NetToolSystem+Mode mode { get; set }`  
- `public Game.Tools.NetToolSystem+Mode actualMode { get }`  
- `public System.Single elevation { get; set }`  
- `public System.Single elevationStep { get; set }`  
- `public System.Int32 parallelCount { get; set }`  
- `public System.Int32 actualParallelCount { get }`  
- `public System.Single parallelOffset { get; set }`  
- `public System.Boolean underground { get; set }`  
- `public System.Boolean allowUnderground { get }`  
- `public Game.Tools.Snap selectedSnap { get; set }`  
- `public Game.Prefabs.NetPrefab prefab { get; set }`  
- `public Game.Prefabs.NetLanePrefab lane { get; set }`  
- `public System.Boolean upgradeOnly { get; private set }`  
- `public System.Boolean allowParallel { get; private set }`  
- `public System.Boolean allowGrid { get; private set }`  
- `public System.Boolean allowReplace { get; private set }`  
- `public System.Boolean serviceUpgrade { get; private set }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

## Constructors

- `public NetToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static AddControlPoints(Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> upgradeStates, Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> appliedUpgrade, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Tools.Snap snap, System.Boolean removeUpgrade, System.Boolean leftHandTraffic, System.Boolean editorMode, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.RoadData prefabRoadData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Net.SubReplacement subReplacement, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Composition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& compositionData, Unity.Entities.ComponentLookup`1[[Game.Net.Upgraded, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& upgradedData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetCompositionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCompositionData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.RoadComposition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRoadCompositionData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData, Unity.Entities.BufferLookup`1[[Game.Net.SubReplacement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subReplacementData) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private CheckElevationRange(Game.Prefabs.PlaceableNetData placeableNetData) : System.Void`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public static CreatePath(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Prefabs.NetData prefabNetData, Game.Prefabs.PlaceableNetData placeableNetData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetDatas, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData) : System.Void`  
- `public virtual ElevationDown() : System.Void`  
- `public virtual ElevationScroll() : System.Void`  
- `public virtual ElevationUp() : System.Void`  
- `private FilterRaycastResult(Unity.Entities.Entity entity, Game.Common.RaycastHit hit) : Game.Tools.ControlPoint`  
- `private FixControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `protected virtual GetAllowApply() : System.Boolean`  
- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `private static GetAvailableSnapMask(Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Tools.NetToolSystem+Mode mode, System.Boolean editorMode, System.Boolean laneContainer, System.Boolean underground, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `public GetControlPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  
- `private static GetMaxControlPointCount(Game.Tools.NetToolSystem+Mode mode) : System.Int32`  
- `private GetNetPrefab() : Game.Prefabs.NetPrefab`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  
- `public GetSnapLines(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.SnapLine>`  
- `private GetSurfaceHeights(Game.Prefabs.NetPrefab prefab, System.Single& overground, System.Single& underground) : System.Void`  
- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  
- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  
- `public virtual InitializeRaycast() : System.Void`  
- `private static IsNearEnd(Unity.Entities.Entity edge, Game.Net.Curve curve, Unity.Mathematics.float3 position, System.Boolean invert, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData) : System.Boolean`  
- `private LoadToolPreferences() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public ResetToolPreferences() : System.Void`  
- `private SaveToolPreferences() : System.Void`  
- `private SetAppliedUpgrade(System.Boolean removing) : System.Void`  
- `public virtual SetUnderground(System.Boolean underground) : System.Void`  
- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade) : Unity.Jobs.JobHandle`  
- `private static TryIntersectLineWithPlane(Colossal.Mathematics.Line3 line, Colossal.Mathematics.Triangle3 plane, System.Single minDot, System.Single& d) : System.Boolean`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateCourse(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade) : Unity.Jobs.JobHandle`  
- `private UpdateStartEntity(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.NetToolSystem+Mode`  
- `Game.Tools.NetToolSystem+NetToolPreferences`  
- `Game.Tools.NetToolSystem+State`  
- `Game.Tools.NetToolSystem+UpgradeState`  
- `Game.Tools.NetToolSystem+PathEdge`  
- `Game.Tools.NetToolSystem+PathItem`  
- `Game.Tools.NetToolSystem+UpdateStartEntityJob`  
- `Game.Tools.NetToolSystem+AppliedUpgrade`  
- `Game.Tools.NetToolSystem+SnapJob`  
- `Game.Tools.NetToolSystem+FixControlPointsJob`  
- `Game.Tools.NetToolSystem+CreateDefinitionsJob`  
- `Game.Tools.NetToolSystem+TypeHandle`  
- `Game.Tools.NetToolSystem+<get_toolActions>d__98`  

