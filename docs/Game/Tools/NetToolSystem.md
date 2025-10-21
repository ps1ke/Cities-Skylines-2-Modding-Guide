# Game.Tools.NetToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private System.Boolean m_LoadingPreferences;
    private Game.Tools.NetToolSystem+Mode m_Mode;
    private System.Single m_Elevation;
    private System.Single m_LastMouseElevation;
    private System.Single m_ElevationStep;
    private System.Int32 m_ParallelCount;
    private System.Single m_ParallelOffset;
    private System.Boolean m_Underground;
    private Game.Tools.Snap m_SelectedSnap;
    private System.Boolean <upgradeOnly>k__BackingField;
    private System.Boolean <allowParallel>k__BackingField;
    private System.Boolean <allowGrid>k__BackingField;
    private System.Boolean <allowReplace>k__BackingField;
    private System.Boolean <serviceUpgrade>k__BackingField;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Prefabs.NetInitializeSystem m_NetInitializeSystem;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_ContainerQuery;
    private Game.Input.IProxyAction m_DowngradeNetEdge;
    private Game.Input.IProxyAction m_PlaceNetControlPoint;
    private Game.Input.IProxyAction m_PlaceNetEdge;
    private Game.Input.IProxyAction m_PlaceNetNode;
    private Game.Input.IProxyAction m_ReplaceNetEdge;
    private Game.Input.IProxyAction m_UndoNetControlPoint;
    private Game.Input.IProxyAction m_UpgradeNetEdge;
    private Game.Input.IProxyAction m_DiscardUpgrade;
    private Game.Input.IProxyAction m_DiscardDowngrade;
    private Game.Input.IProxyAction m_DiscardReplace;
    private System.Boolean m_ApplyBlocked;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Unity.Collections.NativeList<Game.Tools.SnapLine> m_SnapLines;
    private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates;
    private Unity.Collections.NativeReference<Unity.Entities.Entity> m_StartEntity;
    private Unity.Collections.NativeReference<Unity.Entities.Entity> m_LastSnappedEntity;
    private Unity.Collections.NativeReference<System.Int32> m_LastControlPointsAngle;
    private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Game.Tools.ControlPoint m_ApplyStartPoint;
    private Game.Tools.NetToolSystem+State m_State;
    private Colossal.Mathematics.Bounds1 m_LastElevationRange;
    private Game.Tools.NetToolSystem+Mode m_LastActualMode;
    private System.Single m_ApplyTimer;
    private Game.Prefabs.NetPrefab m_Prefab;
    private Game.Prefabs.NetPrefab m_SelectedPrefab;
    private Game.Prefabs.NetLanePrefab m_LanePrefab;
    private System.Boolean m_AllowUndergroundReplace;
    private System.Boolean m_ForceCancel;
    private Game.Common.RandomSeed m_RandomSeed;
    private Game.Tools.NetToolSystem+NetToolPreferences m_DefaultToolPreferences;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Tools.NetToolSystem+NetToolPreferences> m_ToolPreferences;
    private Game.Tools.NetToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public Game.Tools.NetToolSystem+Mode mode { get; set; }
    public Game.Tools.NetToolSystem+Mode actualMode { get; }
    public System.Single elevation { get; set; }
    public System.Single elevationStep { get; set; }
    public System.Int32 parallelCount { get; set; }
    public System.Int32 actualParallelCount { get; }
    public System.Single parallelOffset { get; set; }
    public System.Boolean underground { get; set; }
    public System.Boolean allowUnderground { get; }
    public Game.Tools.Snap selectedSnap { get; set; }
    public Game.Prefabs.NetPrefab prefab { get; set; }
    public Game.Prefabs.NetLanePrefab lane { get; set; }
    public System.Boolean upgradeOnly { get; private set; }
    public System.Boolean allowParallel { get; private set; }
    public System.Boolean allowGrid { get; private set; }
    public System.Boolean allowReplace { get; private set; }
    public System.Boolean serviceUpgrade { get; private set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public NetToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Void AddControlPoints(Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> upgradeStates, Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> appliedUpgrade, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Tools.Snap snap, System.Boolean removeUpgrade, System.Boolean leftHandTraffic, System.Boolean editorMode, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.RoadData prefabRoadData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Net.SubReplacement subReplacement, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Composition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& compositionData, Unity.Entities.ComponentLookup`1[[Game.Net.Upgraded, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& upgradedData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetCompositionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCompositionData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.RoadComposition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRoadCompositionData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData, Unity.Entities.BufferLookup`1[[Game.Net.SubReplacement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subReplacementData);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private System.Void CheckElevationRange(Game.Prefabs.PlaceableNetData placeableNetData);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public static System.Void CreatePath(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Prefabs.NetData prefabNetData, Game.Prefabs.PlaceableNetData placeableNetData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetDatas, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    private Game.Tools.ControlPoint FilterRaycastResult(Unity.Entities.Entity entity, Game.Common.RaycastHit hit);
    private Unity.Jobs.JobHandle FixControlPoints(Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Boolean GetAllowApply();
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    private static System.Void GetAvailableSnapMask(Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Tools.NetToolSystem+Mode mode, System.Boolean editorMode, System.Boolean laneContainer, System.Boolean underground, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Jobs.JobHandle& dependencies);
    private static System.Int32 GetMaxControlPointCount(Game.Tools.NetToolSystem+Mode mode);
    private Game.Prefabs.NetPrefab GetNetPrefab();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    public Unity.Collections.NativeList<Game.Tools.SnapLine> GetSnapLines(Unity.Jobs.JobHandle& dependencies);
    private System.Void GetSurfaceHeights(Game.Prefabs.NetPrefab prefab, System.Single& overground, System.Single& underground);
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    public virtual System.Void InitializeRaycast();
    private static System.Boolean IsNearEnd(Unity.Entities.Entity edge, Game.Net.Curve curve, Unity.Mathematics.float3 position, System.Boolean invert, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData);
    private System.Void LoadToolPreferences();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public System.Void ResetToolPreferences();
    private System.Void SaveToolPreferences();
    private System.Void SetAppliedUpgrade(System.Boolean removing);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade);
    private static System.Boolean TryIntersectLineWithPlane(Colossal.Mathematics.Line3 line, Colossal.Mathematics.Triangle3 plane, System.Single minDot, System.Single& d);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateCourse(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade);
    private Unity.Jobs.JobHandle UpdateStartEntity(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private System.Boolean m_LoadingPreferences`  

```csharp
private System.Boolean m_LoadingPreferences;
```

- `private Game.Tools.NetToolSystem+Mode m_Mode`  

```csharp
private Game.Tools.NetToolSystem+Mode m_Mode;
```

- `private System.Single m_Elevation`  

```csharp
private System.Single m_Elevation;
```

- `private System.Single m_LastMouseElevation`  

```csharp
private System.Single m_LastMouseElevation;
```

- `private System.Single m_ElevationStep`  

```csharp
private System.Single m_ElevationStep;
```

- `private System.Int32 m_ParallelCount`  

```csharp
private System.Int32 m_ParallelCount;
```

- `private System.Single m_ParallelOffset`  

```csharp
private System.Single m_ParallelOffset;
```

- `private System.Boolean m_Underground`  

```csharp
private System.Boolean m_Underground;
```

- `private Game.Tools.Snap m_SelectedSnap`  

```csharp
private Game.Tools.Snap m_SelectedSnap;
```

- `private System.Boolean <upgradeOnly>k__BackingField`  

```csharp
private System.Boolean <upgradeOnly>k__BackingField;
```

- `private System.Boolean <allowParallel>k__BackingField`  

```csharp
private System.Boolean <allowParallel>k__BackingField;
```

- `private System.Boolean <allowGrid>k__BackingField`  

```csharp
private System.Boolean <allowGrid>k__BackingField;
```

- `private System.Boolean <allowReplace>k__BackingField`  

```csharp
private System.Boolean <allowReplace>k__BackingField;
```

- `private System.Boolean <serviceUpgrade>k__BackingField`  

```csharp
private System.Boolean <serviceUpgrade>k__BackingField;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
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

- `private Game.Prefabs.NetInitializeSystem m_NetInitializeSystem`  

```csharp
private Game.Prefabs.NetInitializeSystem m_NetInitializeSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_ContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContainerQuery;
```

- `private Game.Input.IProxyAction m_DowngradeNetEdge`  

```csharp
private Game.Input.IProxyAction m_DowngradeNetEdge;
```

- `private Game.Input.IProxyAction m_PlaceNetControlPoint`  

```csharp
private Game.Input.IProxyAction m_PlaceNetControlPoint;
```

- `private Game.Input.IProxyAction m_PlaceNetEdge`  

```csharp
private Game.Input.IProxyAction m_PlaceNetEdge;
```

- `private Game.Input.IProxyAction m_PlaceNetNode`  

```csharp
private Game.Input.IProxyAction m_PlaceNetNode;
```

- `private Game.Input.IProxyAction m_ReplaceNetEdge`  

```csharp
private Game.Input.IProxyAction m_ReplaceNetEdge;
```

- `private Game.Input.IProxyAction m_UndoNetControlPoint`  

```csharp
private Game.Input.IProxyAction m_UndoNetControlPoint;
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

- `private Game.Input.IProxyAction m_DiscardReplace`  

```csharp
private Game.Input.IProxyAction m_DiscardReplace;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Unity.Collections.NativeList<Game.Tools.SnapLine> m_SnapLines`  

```csharp
private Unity.Collections.NativeList<Game.Tools.SnapLine> m_SnapLines;
```

- `private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates`  

```csharp
private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates;
```

- `private Unity.Collections.NativeReference<Unity.Entities.Entity> m_StartEntity`  

```csharp
private Unity.Collections.NativeReference<Unity.Entities.Entity> m_StartEntity;
```

- `private Unity.Collections.NativeReference<Unity.Entities.Entity> m_LastSnappedEntity`  

```csharp
private Unity.Collections.NativeReference<Unity.Entities.Entity> m_LastSnappedEntity;
```

- `private Unity.Collections.NativeReference<System.Int32> m_LastControlPointsAngle`  

```csharp
private Unity.Collections.NativeReference<System.Int32> m_LastControlPointsAngle;
```

- `private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade`  

```csharp
private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Game.Tools.ControlPoint m_ApplyStartPoint`  

```csharp
private Game.Tools.ControlPoint m_ApplyStartPoint;
```

- `private Game.Tools.NetToolSystem+State m_State`  

```csharp
private Game.Tools.NetToolSystem+State m_State;
```

- `private Colossal.Mathematics.Bounds1 m_LastElevationRange`  

```csharp
private Colossal.Mathematics.Bounds1 m_LastElevationRange;
```

- `private Game.Tools.NetToolSystem+Mode m_LastActualMode`  

```csharp
private Game.Tools.NetToolSystem+Mode m_LastActualMode;
```

- `private System.Single m_ApplyTimer`  

```csharp
private System.Single m_ApplyTimer;
```

- `private Game.Prefabs.NetPrefab m_Prefab`  

```csharp
private Game.Prefabs.NetPrefab m_Prefab;
```

- `private Game.Prefabs.NetPrefab m_SelectedPrefab`  

```csharp
private Game.Prefabs.NetPrefab m_SelectedPrefab;
```

- `private Game.Prefabs.NetLanePrefab m_LanePrefab`  

```csharp
private Game.Prefabs.NetLanePrefab m_LanePrefab;
```

- `private System.Boolean m_AllowUndergroundReplace`  

```csharp
private System.Boolean m_AllowUndergroundReplace;
```

- `private System.Boolean m_ForceCancel`  

```csharp
private System.Boolean m_ForceCancel;
```

- `private Game.Common.RandomSeed m_RandomSeed`  

```csharp
private Game.Common.RandomSeed m_RandomSeed;
```

- `private Game.Tools.NetToolSystem+NetToolPreferences m_DefaultToolPreferences`  

```csharp
private Game.Tools.NetToolSystem+NetToolPreferences m_DefaultToolPreferences;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Tools.NetToolSystem+NetToolPreferences> m_ToolPreferences`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Tools.NetToolSystem+NetToolPreferences> m_ToolPreferences;
```

- `private Game.Tools.NetToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.NetToolSystem+TypeHandle __TypeHandle;
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

- `public Game.Tools.NetToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.NetToolSystem+Mode mode { get; set; }
```

- `public Game.Tools.NetToolSystem+Mode actualMode { get }`  

```csharp
public Game.Tools.NetToolSystem+Mode actualMode { get; }
```

- `public System.Single elevation { get; set }`  

```csharp
public System.Single elevation { get; set; }
```

- `public System.Single elevationStep { get; set }`  

```csharp
public System.Single elevationStep { get; set; }
```

- `public System.Int32 parallelCount { get; set }`  

```csharp
public System.Int32 parallelCount { get; set; }
```

- `public System.Int32 actualParallelCount { get }`  

```csharp
public System.Int32 actualParallelCount { get; }
```

- `public System.Single parallelOffset { get; set }`  

```csharp
public System.Single parallelOffset { get; set; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean allowUnderground { get }`  

```csharp
public System.Boolean allowUnderground { get; }
```

- `public Game.Tools.Snap selectedSnap { get; set }`  

```csharp
public Game.Tools.Snap selectedSnap { get; set; }
```

- `public Game.Prefabs.NetPrefab prefab { get; set }`  

```csharp
public Game.Prefabs.NetPrefab prefab { get; set; }
```

- `public Game.Prefabs.NetLanePrefab lane { get; set }`  

```csharp
public Game.Prefabs.NetLanePrefab lane { get; set; }
```

- `public System.Boolean upgradeOnly { get; private set }`  

```csharp
public System.Boolean upgradeOnly { get; private set; }
```

- `public System.Boolean allowParallel { get; private set }`  

```csharp
public System.Boolean allowParallel { get; private set; }
```

- `public System.Boolean allowGrid { get; private set }`  

```csharp
public System.Boolean allowGrid { get; private set; }
```

- `public System.Boolean allowReplace { get; private set }`  

```csharp
public System.Boolean allowReplace { get; private set; }
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

- `public NetToolSystem()`  

```csharp
public NetToolSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static AddControlPoints(Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> upgradeStates, Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> appliedUpgrade, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Tools.Snap snap, System.Boolean removeUpgrade, System.Boolean leftHandTraffic, System.Boolean editorMode, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.RoadData prefabRoadData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Net.SubReplacement subReplacement, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Composition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& compositionData, Unity.Entities.ComponentLookup`1[[Game.Net.Upgraded, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& upgradedData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetCompositionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCompositionData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.RoadComposition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRoadCompositionData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData, Unity.Entities.BufferLookup`1[[Game.Net.SubReplacement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subReplacementData) : System.Void`  

```csharp
public static System.Void AddControlPoints(Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> upgradeStates, Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> appliedUpgrade, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Tools.Snap snap, System.Boolean removeUpgrade, System.Boolean leftHandTraffic, System.Boolean editorMode, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.RoadData prefabRoadData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Net.SubReplacement subReplacement, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Composition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& compositionData, Unity.Entities.ComponentLookup`1[[Game.Net.Upgraded, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& upgradedData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetCompositionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCompositionData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.RoadComposition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRoadCompositionData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData, Unity.Entities.BufferLookup`1[[Game.Net.SubReplacement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subReplacementData);
```

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
```

- `private CheckElevationRange(Game.Prefabs.PlaceableNetData placeableNetData) : System.Void`  

```csharp
private System.Void CheckElevationRange(Game.Prefabs.PlaceableNetData placeableNetData);
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
```

- `public static CreatePath(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Prefabs.NetData prefabNetData, Game.Prefabs.PlaceableNetData placeableNetData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetDatas, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData) : System.Void`  

```csharp
public static System.Void CreatePath(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Prefabs.NetData prefabNetData, Game.Prefabs.PlaceableNetData placeableNetData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetDatas, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData);
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

- `private FilterRaycastResult(Unity.Entities.Entity entity, Game.Common.RaycastHit hit) : Game.Tools.ControlPoint`  

```csharp
private Game.Tools.ControlPoint FilterRaycastResult(Unity.Entities.Entity entity, Game.Common.RaycastHit hit);
```

- `private FixControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle FixControlPoints(Unity.Jobs.JobHandle inputDeps);
```

- `protected virtual GetAllowApply() : System.Boolean`  

```csharp
protected virtual System.Boolean GetAllowApply();
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `private static GetAvailableSnapMask(Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Tools.NetToolSystem+Mode mode, System.Boolean editorMode, System.Boolean laneContainer, System.Boolean underground, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static System.Void GetAvailableSnapMask(Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Tools.NetToolSystem+Mode mode, System.Boolean editorMode, System.Boolean laneContainer, System.Boolean underground, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `public GetControlPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  

```csharp
public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Jobs.JobHandle& dependencies);
```

- `private static GetMaxControlPointCount(Game.Tools.NetToolSystem+Mode mode) : System.Int32`  

```csharp
private static System.Int32 GetMaxControlPointCount(Game.Tools.NetToolSystem+Mode mode);
```

- `private GetNetPrefab() : Game.Prefabs.NetPrefab`  

```csharp
private Game.Prefabs.NetPrefab GetNetPrefab();
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

- `public GetSnapLines(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.SnapLine>`  

```csharp
public Unity.Collections.NativeList<Game.Tools.SnapLine> GetSnapLines(Unity.Jobs.JobHandle& dependencies);
```

- `private GetSurfaceHeights(Game.Prefabs.NetPrefab prefab, System.Single& overground, System.Single& underground) : System.Void`  

```csharp
private System.Void GetSurfaceHeights(Game.Prefabs.NetPrefab prefab, System.Single& overground, System.Single& underground);
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
```

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public virtual System.Void InitializeRaycast();
```

- `private static IsNearEnd(Unity.Entities.Entity edge, Game.Net.Curve curve, Unity.Mathematics.float3 position, System.Boolean invert, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData) : System.Boolean`  

```csharp
private static System.Boolean IsNearEnd(Unity.Entities.Entity edge, Game.Net.Curve curve, Unity.Mathematics.float3 position, System.Boolean invert, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData);
```

- `private LoadToolPreferences() : System.Void`  

```csharp
private System.Void LoadToolPreferences();
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `public ResetToolPreferences() : System.Void`  

```csharp
public System.Void ResetToolPreferences();
```

- `private SaveToolPreferences() : System.Void`  

```csharp
private System.Void SaveToolPreferences();
```

- `private SetAppliedUpgrade(System.Boolean removing) : System.Void`  

```csharp
private System.Void SetAppliedUpgrade(System.Boolean removing);
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public virtual System.Void SetUnderground(System.Boolean underground);
```

- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade);
```

- `private static TryIntersectLineWithPlane(Colossal.Mathematics.Line3 line, Colossal.Mathematics.Triangle3 plane, System.Single minDot, System.Single& d) : System.Boolean`  

```csharp
private static System.Boolean TryIntersectLineWithPlane(Colossal.Mathematics.Line3 line, Colossal.Mathematics.Triangle3 plane, System.Single minDot, System.Single& d);
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

- `private UpdateCourse(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateCourse(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade);
```

- `private UpdateStartEntity(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateStartEntity(Unity.Jobs.JobHandle inputDeps);
```


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

