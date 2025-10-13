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
[Preserve]
	public NetToolSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public static AddControlPoints(Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> upgradeStates, Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> appliedUpgrade, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Tools.Snap snap, System.Boolean removeUpgrade, System.Boolean leftHandTraffic, System.Boolean editorMode, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.RoadData prefabRoadData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Net.SubReplacement subReplacement, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Composition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& compositionData, Unity.Entities.ComponentLookup`1[[Game.Net.Upgraded, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& upgradedData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetCompositionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCompositionData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.RoadComposition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRoadCompositionData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData, Unity.Entities.BufferLookup`1[[Game.Net.SubReplacement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subReplacementData) : System.Void`  

```csharp
public static void AddControlPoints(NativeList<ControlPoint> controlPoints, NativeList<UpgradeState> upgradeStates, NativeReference<AppliedUpgrade> appliedUpgrade, ControlPoint startPoint, ControlPoint endPoint, NativeList<PathEdge> path, Snap snap, bool removeUpgrade, bool leftHandTraffic, bool editorMode, NetGeometryData prefabGeometryData, RoadData prefabRoadData, PlaceableNetData placeableNetData, SubReplacement subReplacement, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Edge> edgeData, ref ComponentLookup<Game.Net.Node> nodeData, ref ComponentLookup<Curve> curveData, ref ComponentLookup<Composition> compositionData, ref ComponentLookup<Upgraded> upgradedData, ref ComponentLookup<EdgeGeometry> edgeGeometryData, ref ComponentLookup<PrefabRef> prefabRefData, ref ComponentLookup<NetData> prefabNetData, ref ComponentLookup<NetCompositionData> prefabCompositionData, ref ComponentLookup<RoadComposition> prefabRoadCompositionData, ref BufferLookup<ConnectedEdge> connectedEdgeData, ref BufferLookup<SubReplacement> subReplacementData)
	{
		controlPoints.Add(in startPoint);
		float num = 0f;
		float num2 = 0f;
		bool flag = false;
		CompositionFlags.General general = placeableNetData.m_SetUpgradeFlags.m_General | placeableNetData.m_UnsetUpgradeFlags.m_General;
		CompositionFlags.Side side = placeableNetData.m_SetUpgradeFlags.m_Left | placeableNetData.m_SetUpgradeFlags.m_Right | placeableNetData.m_UnsetUpgradeFlags.m_Left | placeableNetData.m_UnsetUpgradeFlags.m_Right;
		if (path.Length != 0)
		{
			PathEdge pathEdge = path[path.Length - 1];
			if (edgeData.HasComponent(pathEdge.m_Entity))
			{
				NetData netData = prefabNetData[prefabRefData[pathEdge.m_Entity].m_Prefab];
				bool flag2 = (netData.m_GeneralFlagMask & general) != 0;
				bool flag3 = (netData.m_SideFlagMask & side) != 0;
				if (pathEdge.m_Upgrade && !flag3)
				{
					flag = true;
				}
				else
				{
					Composition composition = compositionData[pathEdge.m_Entity];
					Curve curve = curveData[pathEdge.m_Entity];
					NetCompositionData netCompositionData = prefabCompositionData[composition.m_Edge];
					num2 = netCompositionData.m_Width * 0.5f;
					MathUtils.Distance(curve.m_Bezier.xz, endPoint.m_HitPosition.xz, out var t);
					float3 @float = MathUtils.Position(curve.m_Bezier, t);
					float3 value = MathUtils.Tangent(curve.m_Bezier, t);
					value = MathUtils.Normalize(value, value.xz);
					num = math.dot(endPoint.m_HitPosition.xz - @float.xz, MathUtils.Right(value.xz));
					num = math.select(num, 0f - num, pathEdge.m_Invert);
					flag = flag2 && math.abs(num) <= netCompositionData.m_Width * (1f / 6f);
				}
			}
		}
		for (int i = 0; i < path.Length; i++)
		{
			PathEdge pathEdge2 = path[i];
			bool flag4 = false;
			Entity entity = pathEdge2.m_Entity;
			Owner componentData;
			while (ownerData.TryGetComponent(entity, out componentData))
			{
				if (edgeData.HasComponent(componentData.m_Owner))
				{
					flag4 = true;
				}
				else if (!editorMode || flag4)
				{
					pathEdge2.m_Entity = Entity.Null;
				}
				entity = componentData.m_Owner;
			}
			if (edgeData.TryGetComponent(pathEdge2.m_Entity, out var componentData2))
			{
				Curve curve2 = curveData[pathEdge2.m_Entity];
				if (pathEdge2.m_Invert)
				{
					CommonUtils.Swap(ref componentData2.m_Start, ref componentData2.m_End);
					curve2.m_Bezier = MathUtils.Invert(curve2.m_Bezier);
				}
				float num3 = 0f;
				if (pathEdge2.m_Upgrade)
				{
					UpgradeState value2 = new UpgradeState
					{
						m_IsUpgrading = true
					};
					if (upgradedData.TryGetComponent(pathEdge2.m_Entity, out var componentData3))
					{
						value2.m_OldFlags = componentData3.m_Flags;
					}
					if (compositionData.TryGetComponent(pathEdge2.m_Entity, out var componentData4))
					{
						if (prefabCompositionData.TryGetComponent(componentData4.m_StartNode, out var componentData5))
						{
							if ((componentData5.m_Flags.m_General & CompositionFlags.General.Crosswalk) != 0)
							{
								if ((componentData5.m_Flags.m_General & CompositionFlags.General.Invert) != 0)
								{
									value2.m_OldFlags.m_Left |= CompositionFlags.Side.AddCrosswalk;
								}
								else
								{
									value2.m_OldFlags.m_Right |= CompositionFlags.Side.AddCrosswalk;
								}
							}
							else if ((componentData5.m_Flags.m_General & CompositionFlags.General.Invert) != 0)
							{
								value2.m_OldFlags.m_Left |= CompositionFlags.Side.RemoveCrosswalk;
							}
							else
							{
								value2.m_OldFlags.m_Right |= CompositionFlags.Side.RemoveCrosswalk;
							}
						}
						if (prefabCompositionData.TryGetComponent(componentData4.m_EndNode, out var componentData6))
						{
							if ((componentData6.m_Flags.m_General & CompositionFlags.General.Crosswalk) != 0)
							{
								if ((componentData6.m_Flags.m_General & CompositionFlags.General.Invert) != 0)
								{
									value2.m_OldFlags.m_Left |= CompositionFlags.Side.AddCrosswalk;
								}
								else
								{
									value2.m_OldFlags.m_Right |= CompositionFlags.Side.AddCrosswalk;
								}
							}
							else if ((componentData6.m_Flags.m_General & CompositionFlags.General.Invert) != 0)
							{
								value2.m_OldFlags.m_Left |= CompositionFlags.Side.RemoveCrosswalk;
							}
							else
							{
								value2.m_OldFlags.m_Right |= CompositionFlags.Side.RemoveCrosswalk;
							}
						}
					}
					CompositionFlags compositionFlags;
					CompositionFlags compositionFlags2;
					if (num < 0f != pathEdge2.m_Invert)
					{
						compositionFlags = NetCompositionHelpers.InvertCompositionFlags(placeableNetData.m_SetUpgradeFlags);
						compositionFlags2 = NetCompositionHelpers.InvertCompositionFlags(placeableNetData.m_UnsetUpgradeFlags);
						value2.m_SubReplacementSide = SubReplacementSide.Left;
					}
					else
					{
						compositionFlags = placeableNetData.m_SetUpgradeFlags;
						compositionFlags2 = placeableNetData.m_UnsetUpgradeFlags;
						value2.m_SubReplacementSide = SubReplacementSide.Right;
					}
					CompositionFlags.Side side2 = CompositionFlags.Side.ForbidLeftTurn | CompositionFlags.Side.ForbidRightTurn | CompositionFlags.Side.AddCrosswalk | CompositionFlags.Side.RemoveCrosswalk | CompositionFlags.Side.ForbidStraight;
					CompositionFlags.Side side3 = (compositionFlags.m_Left | compositionFlags.m_Right) & side2;
					CompositionFlags.Side side4 = (compositionFlags2.m_Left | compositionFlags2.m_Right) & side2;
					if ((side3 | side4) != 0)
					{
						bool2 @bool = false;
						if ((i > 0) & (i < path.Length - 1))
						{
							@bool = true;
						}
						else
						{
							if (i == 0)
							{
								bool flag5 = IsNearEnd(pathEdge2.m_Entity, curve2, startPoint.m_HitPosition, pathEdge2.m_Invert, ref edgeGeometryData);
								@bool |= new bool2(!flag5, flag5);
								if (i + 1 < path.Length && edgeData.TryGetComponent(path[i + 1].m_Entity, out var componentData7))
								{
									@bool |= new bool2((componentData2.m_Start == componentData7.m_Start) | (componentData2.m_Start == componentData7.m_End), (componentData2.m_End == componentData7.m_Start) | (componentData2.m_End == componentData7.m_End));
								}
							}
							if (i == path.Length - 1)
							{
								bool flag6 = IsNearEnd(pathEdge2.m_Entity, curve2, endPoint.m_HitPosition, pathEdge2.m_Invert, ref edgeGeometryData);
								@bool |= new bool2(!flag6, flag6);
								if (i - 1 >= 0 && edgeData.TryGetComponent(path[i - 1].m_Entity, out var componentData8))
								{
									@bool |= new bool2((componentData2.m_Start == componentData8.m_Start) | (componentData2.m_Start == componentData8.m_End), (componentData2.m_End == componentData8.m_Start) | (componentData2.m_End == componentData8.m_End));
								}
							}
						}
						if (pathEdge2.m_Invert != leftHandTraffic)
						{
							@bool = @bool.yx;
						}
						if (@bool.x)
						{
							compositionFlags.m_Left |= side3;
							compositionFlags2.m_Left |= side4;
						}
						else
						{
							compositionFlags.m_Left &= ~side3;
							compositionFlags2.m_Left &= ~side4;
						}
						if (@bool.y)
						{
							compositionFlags.m_Right |= side3;
							compositionFlags2.m_Right |= side4;
						}
						else
						{
							compositionFlags.m_Right &= ~side3;
							compositionFlags2.m_Right &= ~side4;
						}
					}
					NetData netData2 = prefabNetData[prefabRefData[pathEdge2.m_Entity].m_Prefab];
					bool flag7 = (netData2.m_GeneralFlagMask & general) != 0;
					bool flag8 = (netData2.m_SideFlagMask & side) != 0;
					if (flag || !flag8)
					{
						CompositionFlags.Side side5 = ~(CompositionFlags.Side.PrimaryBeautification | CompositionFlags.Side.SecondaryBeautification | CompositionFlags.Side.WideSidewalk);
						compositionFlags.m_Left &= side5;
						compositionFlags.m_Right &= side5;
						compositionFlags2.m_Left &= side5;
						compositionFlags2.m_Right &= side5;
					}
					if (!flag || !flag7)
					{
						CompositionFlags.General general2 = ~(CompositionFlags.General.WideMedian | CompositionFlags.General.PrimaryMiddleBeautification | CompositionFlags.General.SecondaryMiddleBeautification);
						compositionFlags.m_General &= general2;
						compositionFlags2.m_General &= general2;
					}
					if (flag && flag7)
					{
						value2.m_SubReplacementSide = SubReplacementSide.Middle;
						value2.m_SubReplacementType = subReplacement.m_Type;
					}
					else if (!flag && flag8)
					{
						value2.m_SubReplacementType = subReplacement.m_Type;
					}
					if (value2.m_SubReplacementType != SubReplacementType.None)
					{
						if (!removeUpgrade)
						{
							value2.m_SubReplacementPrefab = subReplacement.m_Prefab;
						}
						bool flag9 = false;
						bool flag10 = subReplacement.m_Prefab != Entity.Null;
						if (subReplacementData.TryGetBuffer(pathEdge2.m_Entity, out var bufferData))
						{
							for (int j = 0; j < bufferData.Length; j++)
							{
								SubReplacement subReplacement2 = bufferData[j];
								if (subReplacement2.m_Side == value2.m_SubReplacementSide && subReplacement2.m_Type == value2.m_SubReplacementType)
								{
									flag9 = true;
									flag10 = subReplacement2.m_Prefab != subReplacement.m_Prefab;
									break;
								}
							}
						}
						if (!(removeUpgrade ? flag9 : flag10))
						{
							value2.m_SubReplacementType = SubReplacementType.None;
						}
					}
					if (removeUpgrade)
					{
						compositionFlags2.m_General = (CompositionFlags.General)0u;
						compositionFlags2.m_Left &= CompositionFlags.Side.RemoveCrosswalk;
						compositionFlags2.m_Right &= CompositionFlags.Side.RemoveCrosswalk;
						value2.m_AddFlags = compositionFlags2;
						value2.m_RemoveFlags = compositionFlags;
					}
					else
					{
						value2.m_AddFlags = compositionFlags;
						value2.m_RemoveFlags = compositionFlags2;
					}
					upgradeStates.Add(in value2);
				}
				else
				{
					upgradeStates.Add(default(UpgradeState));
					if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.StrictNodes) == 0)
					{
						num3 = num;
						if ((snap & Snap.ExistingGeometry) != Snap.None)
						{
							Composition composition2 = compositionData[pathEdge2.m_Entity];
							NetCompositionData netCompositionData2 = prefabCompositionData[composition2.m_Edge];
							prefabRoadCompositionData.TryGetComponent(composition2.m_Edge, out var componentData9);
							float num4 = math.abs(netCompositionData2.m_Width - prefabGeometryData.m_DefaultWidth);
							if ((snap & Snap.CellLength) != Snap.None && (componentData9.m_Flags & prefabRoadData.m_Flags & Game.Prefabs.RoadFlags.EnableZoning) != 0)
							{
								int cellWidth = ZoneUtils.GetCellWidth(netCompositionData2.m_Width);
								int cellWidth2 = ZoneUtils.GetCellWidth(prefabGeometryData.m_DefaultWidth);
								float offset = math.select(0f, 4f, ((cellWidth ^ cellWidth2) & 1) != 0);
								num4 = (float)math.abs(cellWidth - cellWidth2) * 8f;
								num3 *= (num4 * 0.5f + 3.92f) / num2;
								num3 = MathUtils.Snap(num3, 8f, offset);
								num3 = math.clamp(num3, num4 * -0.5f, num4 * 0.5f);
							}
							else if (num4 > 1.6f)
							{
								num3 *= num4 * 0.74f / num2;
								num3 = MathUtils.Snap(num3, num4 * 0.5f);
								num3 = math.clamp(num3, num4 * -0.5f, num4 * 0.5f);
							}
							else
							{
								num3 = 0f;
							}
						}
					}
				}
				ControlPoint value3 = endPoint;
				value3.m_OriginalEntity = componentData2.m_Start;
				value3.m_Position = curve2.m_Bezier.a;
				ControlPoint value4 = endPoint;
				value4.m_OriginalEntity = componentData2.m_End;
				value4.m_Position = curve2.m_Bezier.d;
				if (math.abs(num3) >= 0.01f)
				{
					float3 value5 = MathUtils.StartTangent(curve2.m_Bezier);
					float3 value6 = MathUtils.EndTangent(curve2.m_Bezier);
					value5 = MathUtils.Normalize(value5, value5.xz);
					value6 = MathUtils.Normalize(value6, value6.xz);
					value3.m_Position.xz += MathUtils.Right(value5.xz) * num3;
					value4.m_Position.xz += MathUtils.Right(value6.xz) * num3;
				}
				controlPoints.Add(in value3);
				controlPoints.Add(in value4);
			}
			else
			{
				if (!nodeData.TryGetComponent(pathEdge2.m_Entity, out var componentData10))
				{
					continue;
				}
				if (pathEdge2.m_Upgrade)
				{
					UpgradeState value7 = new UpgradeState
					{
						m_IsUpgrading = true
					};
					if (upgradedData.TryGetComponent(pathEdge2.m_Entity, out var componentData11))
					{
						value7.m_OldFlags = componentData11.m_Flags;
					}
					if (connectedEdgeData.TryGetBuffer(pathEdge2.m_Entity, out var bufferData2))
					{
						CompositionFlags compositionFlags3 = default(CompositionFlags);
						for (int k = 0; k < bufferData2.Length; k++)
						{
							Entity edge = bufferData2[k].m_Edge;
							componentData2 = edgeData[edge];
							Composition componentData14;
							NetCompositionData componentData15;
							if (componentData2.m_Start == pathEdge2.m_Entity)
							{
								if (compositionData.TryGetComponent(edge, out var componentData12) && prefabCompositionData.TryGetComponent(componentData12.m_StartNode, out var componentData13))
								{
									compositionFlags3 |= componentData13.m_Flags;
								}
							}
							else if (componentData2.m_End == pathEdge2.m_Entity && compositionData.TryGetComponent(edge, out componentData14) && prefabCompositionData.TryGetComponent(componentData14.m_EndNode, out componentData15))
							{
								compositionFlags3 |= componentData15.m_Flags;
							}
						}
						if ((compositionFlags3.m_General & CompositionFlags.General.TrafficLights) != 0)
						{
							value7.m_OldFlags.m_General |= CompositionFlags.General.TrafficLights;
						}
						else
						{
							value7.m_OldFlags.m_General |= CompositionFlags.General.RemoveTrafficLights;
						}
					}
					CompositionFlags setUpgradeFlags = placeableNetData.m_SetUpgradeFlags;
					CompositionFlags unsetUpgradeFlags = placeableNetData.m_UnsetUpgradeFlags;
					if (removeUpgrade)
					{
						unsetUpgradeFlags.m_General &= CompositionFlags.General.RemoveTrafficLights;
						unsetUpgradeFlags.m_Left = (CompositionFlags.Side)0u;
						unsetUpgradeFlags.m_Right = (CompositionFlags.Side)0u;
						value7.m_AddFlags = unsetUpgradeFlags;
						value7.m_RemoveFlags = setUpgradeFlags;
					}
					else
					{
						value7.m_AddFlags = setUpgradeFlags;
						value7.m_RemoveFlags = unsetUpgradeFlags;
					}
					upgradeStates.Add(in value7);
				}
				else
				{
					upgradeStates.Add(default(UpgradeState));
				}
				ControlPoint value8 = endPoint;
				value8.m_OriginalEntity = pathEdge2.m_Entity;
				value8.m_Position = componentData10.m_Position;
				controlPoints.Add(in value8);
				controlPoints.Add(in value8);
			}
		}
		controlPoints.Add(in endPoint);
		AppliedUpgrade value9 = appliedUpgrade.Value;
		if (value9.m_Entity != Entity.Null)
		{
			if (upgradeStates.Length != 1 || path[path.Length - 1].m_Entity != value9.m_Entity || upgradeStates[0].m_AddFlags != value9.m_Flags || upgradeStates[0].m_SubReplacementSide != value9.m_SubReplacementSide || (subReplacement.m_Type != value9.m_SubReplacementType && value9.m_SubReplacementType != SubReplacementType.None) || (subReplacement.m_Prefab != value9.m_SubReplacementPrefab && value9.m_SubReplacementPrefab != Entity.Null))
			{
				appliedUpgrade.Value = default(AppliedUpgrade);
				return;
			}
			UpgradeState value10 = upgradeStates[0];
			value10.m_SkipFlags = true;
			upgradeStates[0] = value10;
		}
	}
```

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Apply(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		Mode mode = actualMode;
		if (mode == Mode.Replace)
		{
			if (m_State != State.Applying && m_ControlPoints.Length >= 1 && !singleFrameOnly)
			{
				m_State = State.Applying;
				m_AppliedUpgrade.Value = default(AppliedUpgrade);
				return Update(inputDeps, fullUpdate: true);
			}
			m_State = State.Default;
			if (GetAllowApply() && !m_EdgeQuery.IsEmptyIgnoreFilter)
			{
				SetAppliedUpgrade(removing: false);
				base.applyMode = ApplyMode.Apply;
				m_RandomSeed = RandomSeed.Next();
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetBuildSound);
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				if (GetRaycastResult(out var controlPoint))
				{
					controlPoint.m_Elevation = elevation;
					m_ControlPoints.Add(in controlPoint);
					inputDeps = SnapControlPoints(inputDeps, removeUpgrade: false);
					inputDeps = FixControlPoints(inputDeps);
					inputDeps = UpdateCourse(inputDeps, removeUpgrade: false);
				}
				else
				{
					inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
				}
			}
			else
			{
				inputDeps = Update(inputDeps, fullUpdate: true);
			}
			return inputDeps;
		}
		if (m_State != State.Applying && m_ControlPoints.Length >= 1 && !singleFrameOnly)
		{
			m_State = State.Applying;
			m_ApplyStartPoint = m_LastRaycastPoint;
			m_ApplyStartPoint.m_HitPosition.y -= m_ApplyStartPoint.m_Elevation;
			m_ApplyTimer = 0f;
			return Update(inputDeps, fullUpdate: true);
		}
		m_State = State.Default;
		if (m_ControlPoints.Length < mode switch
		{
			Mode.Straight => 2, 
			Mode.SimpleCurve => 3, 
			Mode.ComplexCurve => 4, 
			Mode.Continuous => 3, 
			Mode.Grid => 3, 
			_ => 1, 
		})
		{
			base.applyMode = ApplyMode.Clear;
			if (GetRaycastResult(out var controlPoint2))
			{
				if (m_ControlPoints.Length <= 1)
				{
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetStartSound);
				}
				else
				{
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetNodeSound);
				}
				controlPoint2.m_HitPosition.y += elevation;
				controlPoint2.m_Elevation = elevation;
				m_ControlPoints.Add(in controlPoint2);
				inputDeps = SnapControlPoints(inputDeps, removeUpgrade: false);
				inputDeps = UpdateCourse(inputDeps, removeUpgrade: false);
			}
			else
			{
				inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
			}
		}
		else if (!((mode == Mode.Point) ? m_NodeQuery : m_EdgeQuery).IsEmptyIgnoreFilter)
		{
			if (!GetAllowApply())
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PlaceBuildingFailSound);
			}
			else
			{
				base.applyMode = ApplyMode.Apply;
				m_RandomSeed = RandomSeed.Next();
				int num = 0;
				switch (mode)
				{
				case Mode.Continuous:
				{
					ControlPoint value2 = m_ControlPoints[m_ControlPoints.Length - 2];
					ControlPoint value3 = m_ControlPoints[m_ControlPoints.Length - 1];
					m_ControlPoints.Clear();
					float num2 = math.distance(value2.m_Position.xz, value3.m_Position.xz);
					value2.m_OriginalEntity = Entity.Null;
					value2.m_Direction = value3.m_Direction;
					value2.m_Position = value3.m_Position;
					value2.m_Position.xz += value2.m_Direction * num2;
					m_ControlPoints.Add(in value3);
					num++;
					m_ControlPoints.Add(in value2);
					num++;
					break;
				}
				case Mode.Point:
					m_ControlPoints.Clear();
					break;
				default:
				{
					ControlPoint value = m_ControlPoints[m_ControlPoints.Length - 1];
					m_ControlPoints.Clear();
					m_ControlPoints.Add(in value);
					num++;
					break;
				}
				}
				if (GetRaycastResult(out var controlPoint3))
				{
					controlPoint3.m_HitPosition.y += elevation;
					controlPoint3.m_Elevation = elevation;
					m_ControlPoints.Add(in controlPoint3);
					inputDeps = SnapControlPoints(inputDeps, removeUpgrade: false);
					num++;
				}
				if (num >= 1)
				{
					inputDeps = FixControlPoints(inputDeps);
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetBuildSound);
					inputDeps = UpdateCourse(inputDeps, removeUpgrade: false);
				}
				else
				{
					inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
				}
			}
		}
		else
		{
			inputDeps = Update(inputDeps, fullUpdate: true);
		}
		return inputDeps;
	}
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Cancel(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		if (actualMode == Mode.Replace)
		{
			if (m_State != State.Cancelling && m_ControlPoints.Length >= 1)
			{
				m_State = State.Cancelling;
				m_ForceCancel = singleFrameOnly;
				m_AppliedUpgrade.Value = default(AppliedUpgrade);
				return Update(inputDeps, fullUpdate: true);
			}
			m_State = State.Default;
			if (GetAllowApply() && !m_EdgeQuery.IsEmptyIgnoreFilter)
			{
				SetAppliedUpgrade(removing: true);
				base.applyMode = ApplyMode.Apply;
				m_RandomSeed = RandomSeed.Next();
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				if (GetRaycastResult(out var controlPoint))
				{
					controlPoint.m_Elevation = elevation;
					m_ControlPoints.Add(in controlPoint);
					inputDeps = SnapControlPoints(inputDeps, removeUpgrade: false);
					inputDeps = FixControlPoints(inputDeps);
					inputDeps = UpdateCourse(inputDeps, removeUpgrade: false);
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolRemovePointSound);
				}
				else
				{
					inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
				}
			}
			else
			{
				base.applyMode = ApplyMode.Clear;
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				if (GetRaycastResult(out var controlPoint2))
				{
					controlPoint2.m_Elevation = elevation;
					m_ControlPoints.Add(in controlPoint2);
					inputDeps = SnapControlPoints(inputDeps, removeUpgrade: false);
					inputDeps = UpdateCourse(inputDeps, removeUpgrade: false);
				}
				else
				{
					inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
				}
			}
			return inputDeps;
		}
		m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetCancelSound);
		m_State = State.Default;
		base.applyMode = ApplyMode.Clear;
		m_UpgradeStates.Clear();
		if (m_ControlPoints.Length > 0)
		{
			m_ControlPoints.RemoveAt(m_ControlPoints.Length - 1);
		}
		if (GetRaycastResult(out var controlPoint3))
		{
			controlPoint3.m_HitPosition.y += elevation;
			controlPoint3.m_Elevation = elevation;
			if (m_ControlPoints.Length > 0)
			{
				m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint3;
			}
			else
			{
				m_ControlPoints.Add(in controlPoint3);
			}
			inputDeps = SnapControlPoints(inputDeps, removeUpgrade: false);
			inputDeps = UpdateCourse(inputDeps, removeUpgrade: false);
		}
		else
		{
			inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		}
		return inputDeps;
	}
```

- `private CheckElevationRange(Game.Prefabs.PlaceableNetData placeableNetData) : System.Void`  

```csharp
private void CheckElevationRange(PlaceableNetData placeableNetData)
	{
		if (!placeableNetData.m_ElevationRange.Equals(m_LastElevationRange))
		{
			float position = MathUtils.Clamp(0f, placeableNetData.m_ElevationRange);
			if (!MathUtils.Intersect(m_LastElevationRange, position) || !MathUtils.Intersect(placeableNetData.m_ElevationRange, elevation))
			{
				elevation = position;
			}
			m_LastElevationRange = placeableNetData.m_ElevationRange;
		}
	}
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Clear(JobHandle inputDeps)
	{
		base.applyMode = ApplyMode.Clear;
		inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		return inputDeps;
	}
```

- `public static CreatePath(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Collections.NativeList<Game.Tools.NetToolSystem+PathEdge> path, Game.Prefabs.NetData prefabNetData, Game.Prefabs.PlaceableNetData placeableNetData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Net.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabNetDatas, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdgeData) : System.Void`  

```csharp
public static void CreatePath(ControlPoint startPoint, ControlPoint endPoint, NativeList<PathEdge> path, NetData prefabNetData, PlaceableNetData placeableNetData, ref ComponentLookup<Edge> edgeData, ref ComponentLookup<Game.Net.Node> nodeData, ref ComponentLookup<Curve> curveData, ref ComponentLookup<PrefabRef> prefabRefData, ref ComponentLookup<NetData> prefabNetDatas, ref BufferLookup<ConnectedEdge> connectedEdgeData)
	{
		if (math.distance(startPoint.m_Position, endPoint.m_Position) < placeableNetData.m_SnapDistance * 0.5f)
		{
			endPoint = startPoint;
		}
		CompositionFlags.General general = placeableNetData.m_SetUpgradeFlags.m_General | placeableNetData.m_UnsetUpgradeFlags.m_General;
		CompositionFlags.Side side = placeableNetData.m_SetUpgradeFlags.m_Left | placeableNetData.m_SetUpgradeFlags.m_Right | placeableNetData.m_UnsetUpgradeFlags.m_Left | placeableNetData.m_UnsetUpgradeFlags.m_Right;
		if (startPoint.m_OriginalEntity == endPoint.m_OriginalEntity)
		{
			if (edgeData.HasComponent(endPoint.m_OriginalEntity))
			{
				NetData netData = prefabNetDatas[prefabRefData[endPoint.m_OriginalEntity].m_Prefab];
				bool num = (prefabNetData.m_RequiredLayers & netData.m_RequiredLayers) != 0;
				bool flag = !num && (placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.IsUpgrade) != Game.Net.PlacementFlags.None && (placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.NodeUpgrade) == 0 && ((netData.m_GeneralFlagMask & general) != 0 || (netData.m_SideFlagMask & side) != 0);
				if (num || flag)
				{
					PathEdge value = new PathEdge
					{
						m_Entity = endPoint.m_OriginalEntity,
						m_Invert = (endPoint.m_CurvePosition < startPoint.m_CurvePosition),
						m_Upgrade = flag
					};
					path.Add(in value);
				}
			}
			else
			{
				if (!nodeData.HasComponent(endPoint.m_OriginalEntity))
				{
					return;
				}
				NetData netData2 = prefabNetDatas[prefabRefData[endPoint.m_OriginalEntity].m_Prefab];
				bool flag2 = (prefabNetData.m_RequiredLayers & netData2.m_RequiredLayers) != 0;
				if (flag2)
				{
					DynamicBuffer<ConnectedEdge> dynamicBuffer = connectedEdgeData[endPoint.m_OriginalEntity];
					for (int i = 0; i < dynamicBuffer.Length; i++)
					{
						Entity edge = dynamicBuffer[i].m_Edge;
						Edge edge2 = edgeData[edge];
						if (edge2.m_Start == endPoint.m_OriginalEntity || edge2.m_End == endPoint.m_OriginalEntity)
						{
							flag2 = false;
							break;
						}
					}
				}
				bool flag3 = !flag2 && (placeableNetData.m_PlacementFlags & (Game.Net.PlacementFlags.IsUpgrade | Game.Net.PlacementFlags.NodeUpgrade)) == (Game.Net.PlacementFlags.IsUpgrade | Game.Net.PlacementFlags.NodeUpgrade) && ((netData2.m_GeneralFlagMask & general) != 0 || (netData2.m_SideFlagMask & side) != 0);
				if (flag2 || flag3)
				{
					PathEdge value = new PathEdge
					{
						m_Entity = endPoint.m_OriginalEntity,
						m_Upgrade = flag3
					};
					path.Add(in value);
				}
			}
			return;
		}
		NativeMinHeap<PathItem> nativeMinHeap = new NativeMinHeap<PathItem>(100, Allocator.Temp);
		NativeParallelHashMap<Entity, Entity> nativeParallelHashMap = new NativeParallelHashMap<Entity, Entity>(100, Allocator.Temp);
		if (edgeData.TryGetComponent(endPoint.m_OriginalEntity, out var componentData))
		{
			NetData netData3 = prefabNetDatas[prefabRefData[endPoint.m_OriginalEntity].m_Prefab];
			bool num2 = (prefabNetData.m_RequiredLayers & netData3.m_RequiredLayers) != 0;
			bool flag4 = !num2 && (placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.IsUpgrade) != Game.Net.PlacementFlags.None && ((netData3.m_GeneralFlagMask & general) != 0 || (netData3.m_SideFlagMask & side) != 0);
			if (num2 || flag4)
			{
				nativeMinHeap.Insert(new PathItem
				{
					m_Node = componentData.m_Start,
					m_Edge = endPoint.m_OriginalEntity,
					m_Cost = 0f
				});
				nativeMinHeap.Insert(new PathItem
				{
					m_Node = componentData.m_End,
					m_Edge = endPoint.m_OriginalEntity,
					m_Cost = 0f
				});
			}
		}
		else if (nodeData.HasComponent(endPoint.m_OriginalEntity))
		{
			nativeMinHeap.Insert(new PathItem
			{
				m_Node = endPoint.m_OriginalEntity,
				m_Edge = Entity.Null,
				m_Cost = 0f
			});
		}
		Entity entity = Entity.Null;
		while (nativeMinHeap.Length != 0)
		{
			PathItem pathItem = nativeMinHeap.Extract();
			if (pathItem.m_Edge == startPoint.m_OriginalEntity)
			{
				nativeParallelHashMap[pathItem.m_Node] = pathItem.m_Edge;
				entity = pathItem.m_Node;
				break;
			}
			if (!nativeParallelHashMap.TryAdd(pathItem.m_Node, pathItem.m_Edge))
			{
				continue;
			}
			if (pathItem.m_Node == startPoint.m_OriginalEntity)
			{
				entity = pathItem.m_Node;
				break;
			}
			DynamicBuffer<ConnectedEdge> dynamicBuffer2 = connectedEdgeData[pathItem.m_Node];
			PrefabRef prefabRef = default(PrefabRef);
			if (pathItem.m_Edge != Entity.Null)
			{
				prefabRef = prefabRefData[pathItem.m_Edge];
			}
			for (int j = 0; j < dynamicBuffer2.Length; j++)
			{
				Entity edge3 = dynamicBuffer2[j].m_Edge;
				if (edge3 == pathItem.m_Edge)
				{
					continue;
				}
				componentData = edgeData[edge3];
				Entity entity2;
				if (componentData.m_Start == pathItem.m_Node)
				{
					entity2 = componentData.m_End;
				}
				else
				{
					if (!(componentData.m_End == pathItem.m_Node))
					{
						continue;
					}
					entity2 = componentData.m_Start;
				}
				if (!nativeParallelHashMap.ContainsKey(entity2) || !(edge3 != startPoint.m_OriginalEntity))
				{
					PrefabRef prefabRef2 = prefabRefData[edge3];
					NetData netData4 = prefabNetDatas[prefabRef2.m_Prefab];
					bool num3 = (prefabNetData.m_RequiredLayers & netData4.m_RequiredLayers) != 0;
					bool flag5 = !num3 && (placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.IsUpgrade) != Game.Net.PlacementFlags.None && ((netData4.m_GeneralFlagMask & general) != 0 || (netData4.m_SideFlagMask & side) != 0);
					if (num3 || flag5)
					{
						Curve curve = curveData[edge3];
						float num4 = pathItem.m_Cost + curve.m_Length;
						num4 += math.select(0f, 9.9f, prefabRef2.m_Prefab != prefabRef.m_Prefab);
						num4 += math.select(0f, 10f, dynamicBuffer2.Length > 2);
						nativeMinHeap.Insert(new PathItem
						{
							m_Node = entity2,
							m_Edge = edge3,
							m_Cost = num4
						});
					}
				}
			}
		}
		Entity item;
		while (nativeParallelHashMap.TryGetValue(entity, out item) && !(item == Entity.Null))
		{
			componentData = edgeData[item];
			NetData netData5 = prefabNetDatas[prefabRefData[item].m_Prefab];
			bool flag6 = componentData.m_End == entity;
			bool flag7 = (prefabNetData.m_RequiredLayers & netData5.m_RequiredLayers) != 0;
			Entity entity3 = (flag6 ? componentData.m_Start : componentData.m_End);
			if (flag7 || (placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.NodeUpgrade) == 0)
			{
				PathEdge value = new PathEdge
				{
					m_Entity = item,
					m_Invert = flag6,
					m_Upgrade = !flag7
				};
				path.Add(in value);
			}
			else
			{
				if (entity == startPoint.m_OriginalEntity)
				{
					PathEdge value = new PathEdge
					{
						m_Entity = entity,
						m_Upgrade = true
					};
					path.Add(in value);
				}
				if (item != endPoint.m_OriginalEntity)
				{
					PathEdge value = new PathEdge
					{
						m_Entity = entity3,
						m_Upgrade = true
					};
					path.Add(in value);
				}
			}
			if (!(item == endPoint.m_OriginalEntity))
			{
				entity = entity3;
				continue;
			}
			break;
		}
	}
```

- `public virtual ElevationDown() : System.Void`  

```csharp
public override void ElevationDown()
	{
		NetPrefab netPrefab = GetNetPrefab();
		if (!(netPrefab != null))
		{
			return;
		}
		if (actualMode == Mode.Replace)
		{
			underground = true;
			return;
		}
		m_Prefab = netPrefab;
		if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out var component) && component.m_UndergroundPrefab != Entity.Null && elevation < 0f)
		{
			m_Prefab = m_PrefabSystem.GetPrefab<NetPrefab>(component.m_UndergroundPrefab);
		}
		if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out component))
		{
			CheckElevationRange(component);
			elevation = math.ceil(elevation / elevationStep - 1.00001f) * elevationStep;
			if (elevation < component.m_ElevationRange.min - elevationStep * 0.5f && m_Prefab == netPrefab && component.m_UndergroundPrefab != Entity.Null)
			{
				m_Prefab = m_PrefabSystem.GetPrefab<NetPrefab>(component.m_UndergroundPrefab);
				m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out component);
				CheckElevationRange(component);
			}
		}
	}
```

- `public virtual ElevationScroll() : System.Void`  

```csharp
public override void ElevationScroll()
	{
		NetPrefab netPrefab = GetNetPrefab();
		if (!(netPrefab != null))
		{
			return;
		}
		if (actualMode == Mode.Replace)
		{
			underground = !underground;
			return;
		}
		m_Prefab = netPrefab;
		if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out var component) && component.m_UndergroundPrefab != Entity.Null && elevation < 0f)
		{
			m_Prefab = m_PrefabSystem.GetPrefab<NetPrefab>(component.m_UndergroundPrefab);
		}
		if (!m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out component))
		{
			return;
		}
		elevation = math.floor(elevation / elevationStep + 1.00001f) * elevationStep;
		if (!(elevation > component.m_ElevationRange.max + elevationStep * 0.5f))
		{
			return;
		}
		if (m_Prefab != netPrefab)
		{
			m_Prefab = netPrefab;
			m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out component);
			CheckElevationRange(component);
			return;
		}
		if (component.m_UndergroundPrefab != Entity.Null)
		{
			m_Prefab = m_PrefabSystem.GetPrefab<NetPrefab>(component.m_UndergroundPrefab);
			m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out component);
		}
		elevation = math.ceil(component.m_ElevationRange.min / elevationStep) * elevationStep;
		CheckElevationRange(component);
	}
```

- `public virtual ElevationUp() : System.Void`  

```csharp
public override void ElevationUp()
	{
		NetPrefab netPrefab = GetNetPrefab();
		if (!(netPrefab != null))
		{
			return;
		}
		if (actualMode == Mode.Replace)
		{
			underground = false;
			return;
		}
		m_Prefab = netPrefab;
		if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out var component) && component.m_UndergroundPrefab != Entity.Null && elevation < 0f)
		{
			m_Prefab = m_PrefabSystem.GetPrefab<NetPrefab>(component.m_UndergroundPrefab);
		}
		if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out component))
		{
			CheckElevationRange(component);
			elevation = math.floor(elevation / elevationStep + 1.00001f) * elevationStep;
			if (elevation > component.m_ElevationRange.max + elevationStep * 0.5f && m_Prefab != netPrefab)
			{
				m_Prefab = netPrefab;
				m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out component);
				CheckElevationRange(component);
			}
		}
	}
```

- `private FilterRaycastResult(Unity.Entities.Entity entity, Game.Common.RaycastHit hit) : Game.Tools.ControlPoint`  

```csharp
private ControlPoint FilterRaycastResult(Entity entity, RaycastHit hit)
	{
		if (actualMode == Mode.Replace)
		{
			if (base.EntityManager.HasComponent<Game.Net.Node>(entity) && base.EntityManager.HasComponent<Edge>(hit.m_HitEntity) && m_PrefabSystem.TryGetComponentData<PlaceableNetData>(prefab, out var component) && (component.m_PlacementFlags & Game.Net.PlacementFlags.NodeUpgrade) == 0)
			{
				entity = hit.m_HitEntity;
			}
			bool flag = false;
			Entity entity2 = entity;
			Owner component2;
			while (base.EntityManager.TryGetComponent<Owner>(entity2, out component2))
			{
				if (base.EntityManager.HasComponent<Edge>(component2.m_Owner))
				{
					flag = true;
				}
				else if (!m_ToolSystem.actionMode.IsEditor() || flag)
				{
					return default(ControlPoint);
				}
				entity2 = component2.m_Owner;
			}
		}
		return new ControlPoint(entity, hit);
	}
```

- `private FixControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle FixControlPoints(JobHandle inputDeps)
	{
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_TempQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new FixControlPointsJob
		{
			m_Chunks = chunks,
			m_Mode = mode,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControlPoints = m_ControlPoints
		}, JobHandle.CombineDependencies(inputDeps, outJobHandle));
		chunks.Dispose(jobHandle);
		return jobHandle;
	}
```

- `protected virtual GetAllowApply() : System.Boolean`  

```csharp
protected override bool GetAllowApply()
	{
		Mode mode = actualMode;
		if (mode != Mode.Replace)
		{
			NativeArray<ArchetypeChunk> nativeArray = m_EdgeQuery.ToArchetypeChunkArray(Allocator.Temp);
			NativeArray<ArchetypeChunk> nativeArray2 = m_NodeQuery.ToArchetypeChunkArray(Allocator.Temp);
			NativeHashSet<Entity> nativeHashSet = new NativeHashSet<Entity>(100, Allocator.Temp);
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Edge> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Owner> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Temp> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			CompleteDependency();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Edge> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<Temp> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle3);
				for (int j = 0; j < nativeArray3.Length; j++)
				{
					if ((nativeArray4[j].m_Flags & TempFlags.Create) != 0)
					{
						Edge edge = nativeArray3[j];
						nativeHashSet.Add(edge.m_Start);
						nativeHashSet.Add(edge.m_End);
					}
				}
			}
			if (mode != Mode.Point && m_ControlPoints.Length > 1 && nativeHashSet.IsEmpty)
			{
				return false;
			}
			for (int k = 0; k < nativeArray2.Length; k++)
			{
				ArchetypeChunk archetypeChunk2 = nativeArray2[k];
				NativeArray<Entity> nativeArray5 = archetypeChunk2.GetNativeArray(entityTypeHandle);
				NativeArray<Owner> nativeArray6 = archetypeChunk2.GetNativeArray(ref typeHandle2);
				NativeArray<Temp> nativeArray7 = archetypeChunk2.GetNativeArray(ref typeHandle3);
				for (int l = 0; l < nativeArray5.Length; l++)
				{
					Entity item = nativeArray5[l];
					Temp temp = nativeArray7[l];
					if ((temp.m_Flags & (TempFlags.Create | TempFlags.Replace)) != 0 && (temp.m_Flags & TempFlags.Essential) != 0 && !nativeHashSet.Contains(item) && ((mode != Mode.Point && m_ControlPoints.Length > 1) || (CollectionUtils.TryGet(nativeArray6, l, out var value) && value.m_Owner == Entity.Null && (mode == Mode.Point || m_ControlPoints.Length > 1))))
					{
						return false;
					}
				}
			}
			nativeArray.Dispose();
			nativeArray2.Dispose();
			nativeHashSet.Dispose();
			return base.GetAllowApply();
		}
		if (m_ControlPoints.Length >= 1)
		{
			return base.GetAllowApply();
		}
		return false;
	}
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static void GetAvailableSnapMask(NetGeometryData prefabGeometryData, PlaceableNetData placeableNetData, Mode mode, bool editorMode, bool laneContainer, bool underground, out Snap onMask, out Snap offMask)
	{
		if (mode == Mode.Replace)
		{
			onMask = Snap.ExistingGeometry;
			offMask = onMask;
			if ((placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.UpgradeOnly) == 0)
			{
				onMask |= Snap.ContourLines;
				offMask |= Snap.ContourLines;
			}
			if (laneContainer)
			{
				onMask &= ~Snap.ExistingGeometry;
				offMask &= ~Snap.ExistingGeometry;
				onMask |= Snap.NearbyGeometry;
				return;
			}
			if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.StrictNodes) != 0)
			{
				offMask &= ~Snap.ExistingGeometry;
			}
			if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.SnapCellSize) != 0)
			{
				onMask |= Snap.CellLength;
				offMask |= Snap.CellLength;
			}
			return;
		}
		onMask = Snap.ExistingGeometry | Snap.CellLength | Snap.StraightDirection | Snap.ObjectSide | Snap.GuideLines | Snap.ZoneGrid | Snap.ContourLines;
		offMask = onMask;
		if (underground)
		{
			onMask &= ~(Snap.ObjectSide | Snap.ZoneGrid);
		}
		else if ((placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.ShoreLine) != Game.Net.PlacementFlags.None)
		{
			onMask |= Snap.Shoreline;
			offMask |= Snap.Shoreline;
		}
		if (laneContainer)
		{
			onMask &= ~(Snap.CellLength | Snap.ObjectSide);
			offMask &= ~(Snap.CellLength | Snap.ObjectSide);
		}
		else if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.Marker) != 0)
		{
			onMask &= ~Snap.ObjectSide;
			offMask &= ~Snap.ObjectSide;
		}
		if (laneContainer)
		{
			onMask &= ~Snap.ExistingGeometry;
			offMask &= ~Snap.ExistingGeometry;
			onMask |= Snap.NearbyGeometry;
			offMask |= Snap.NearbyGeometry;
		}
		else if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.StrictNodes) != 0)
		{
			offMask &= ~Snap.ExistingGeometry;
			onMask |= Snap.NearbyGeometry;
			offMask |= Snap.NearbyGeometry;
		}
		if (editorMode)
		{
			onMask |= Snap.ObjectSurface | Snap.LotGrid | Snap.AutoParent;
			offMask |= Snap.ObjectSurface | Snap.LotGrid | Snap.AutoParent;
		}
	}
```

- `private static GetAvailableSnapMask(Game.Prefabs.NetGeometryData prefabGeometryData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Tools.NetToolSystem+Mode mode, System.Boolean editorMode, System.Boolean laneContainer, System.Boolean underground, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static void GetAvailableSnapMask(NetGeometryData prefabGeometryData, PlaceableNetData placeableNetData, Mode mode, bool editorMode, bool laneContainer, bool underground, out Snap onMask, out Snap offMask)
	{
		if (mode == Mode.Replace)
		{
			onMask = Snap.ExistingGeometry;
			offMask = onMask;
			if ((placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.UpgradeOnly) == 0)
			{
				onMask |= Snap.ContourLines;
				offMask |= Snap.ContourLines;
			}
			if (laneContainer)
			{
				onMask &= ~Snap.ExistingGeometry;
				offMask &= ~Snap.ExistingGeometry;
				onMask |= Snap.NearbyGeometry;
				return;
			}
			if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.StrictNodes) != 0)
			{
				offMask &= ~Snap.ExistingGeometry;
			}
			if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.SnapCellSize) != 0)
			{
				onMask |= Snap.CellLength;
				offMask |= Snap.CellLength;
			}
			return;
		}
		onMask = Snap.ExistingGeometry | Snap.CellLength | Snap.StraightDirection | Snap.ObjectSide | Snap.GuideLines | Snap.ZoneGrid | Snap.ContourLines;
		offMask = onMask;
		if (underground)
		{
			onMask &= ~(Snap.ObjectSide | Snap.ZoneGrid);
		}
		else if ((placeableNetData.m_PlacementFlags & Game.Net.PlacementFlags.ShoreLine) != Game.Net.PlacementFlags.None)
		{
			onMask |= Snap.Shoreline;
			offMask |= Snap.Shoreline;
		}
		if (laneContainer)
		{
			onMask &= ~(Snap.CellLength | Snap.ObjectSide);
			offMask &= ~(Snap.CellLength | Snap.ObjectSide);
		}
		else if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.Marker) != 0)
		{
			onMask &= ~Snap.ObjectSide;
			offMask &= ~Snap.ObjectSide;
		}
		if (laneContainer)
		{
			onMask &= ~Snap.ExistingGeometry;
			offMask &= ~Snap.ExistingGeometry;
			onMask |= Snap.NearbyGeometry;
			offMask |= Snap.NearbyGeometry;
		}
		else if ((prefabGeometryData.m_Flags & Game.Net.GeometryFlags.StrictNodes) != 0)
		{
			offMask &= ~Snap.ExistingGeometry;
			onMask |= Snap.NearbyGeometry;
			offMask |= Snap.NearbyGeometry;
		}
		if (editorMode)
		{
			onMask |= Snap.ObjectSurface | Snap.LotGrid | Snap.AutoParent;
			offMask |= Snap.ObjectSurface | Snap.LotGrid | Snap.AutoParent;
		}
	}
```

- `public GetControlPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  

```csharp
public NativeList<ControlPoint> GetControlPoints(out JobHandle dependencies)
	{
		dependencies = base.Dependency;
		return m_ControlPoints;
	}
```

- `private static GetMaxControlPointCount(Game.Tools.NetToolSystem+Mode mode) : System.Int32`  

```csharp
private static int GetMaxControlPointCount(Mode mode)
	{
		switch (mode)
		{
		case Mode.Straight:
			return 2;
		case Mode.SimpleCurve:
		case Mode.Continuous:
		case Mode.Grid:
			return 3;
		case Mode.ComplexCurve:
			return 4;
		default:
			return 1;
		}
	}
```

- `private GetNetPrefab() : Game.Prefabs.NetPrefab`  

```csharp
private NetPrefab GetNetPrefab()
	{
		if (m_ToolSystem.actionMode.IsEditor() && m_LanePrefab != null && GetContainers(m_ContainerQuery, out var laneContainer, out var _))
		{
			return m_PrefabSystem.GetPrefab<NetPrefab>(laneContainer);
		}
		return m_SelectedPrefab;
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		if (!(prefab != null))
		{
			return lane;
		}
		return prefab;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected override bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			controlPoint = FilterRaycastResult(entity, hit);
			return controlPoint.m_OriginalEntity != Entity.Null;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected override bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			controlPoint = FilterRaycastResult(entity, hit);
			return controlPoint.m_OriginalEntity != Entity.Null;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `public GetSnapLines(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.SnapLine>`  

```csharp
public NativeList<SnapLine> GetSnapLines(out JobHandle dependencies)
	{
		dependencies = base.Dependency;
		return m_SnapLines;
	}
```

- `private GetSurfaceHeights(Game.Prefabs.NetPrefab prefab, System.Single& overground, System.Single& underground) : System.Void`  

```csharp
private void GetSurfaceHeights(NetPrefab prefab, out float overground, out float underground)
	{
		overground = 0f;
		underground = 0f;
		if (m_PrefabSystem.TryGetComponentData<NetGeometryData>(prefab, out var component))
		{
			overground = component.m_DefaultSurfaceHeight.max;
			underground = component.m_DefaultSurfaceHeight.max;
		}
		if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(prefab, out var component2) && component2.m_UndergroundPrefab != Entity.Null)
		{
			NetPrefab netPrefab = m_PrefabSystem.GetPrefab<NetPrefab>(component2.m_UndergroundPrefab);
			if (m_PrefabSystem.TryGetComponentData<NetGeometryData>(netPrefab, out var component3))
			{
				underground = component3.m_DefaultSurfaceHeight.max;
			}
		}
	}
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public override void GetUIModes(List<ToolMode> modes)
	{
		if (upgradeOnly)
		{
			modes.Add(new ToolMode(Mode.Replace.ToString(), 5));
			return;
		}
		modes.Add(new ToolMode(Mode.Straight.ToString(), 0));
		modes.Add(new ToolMode(Mode.SimpleCurve.ToString(), 1));
		modes.Add(new ToolMode(Mode.ComplexCurve.ToString(), 2));
		modes.Add(new ToolMode(Mode.Continuous.ToString(), 3));
		if (allowGrid)
		{
			modes.Add(new ToolMode(Mode.Grid.ToString(), 4));
		}
		if (allowReplace)
		{
			modes.Add(new ToolMode(Mode.Replace.ToString(), 5));
		}
		if (m_ToolSystem.actionMode.IsEditor())
		{
			modes.Add(new ToolMode(Mode.Point.ToString(), 6));
		}
	}
```

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Entity GetUpgradable(Entity entity)
	{
		if (base.EntityManager.TryGetComponent<Attached>(entity, out var component))
		{
			return component.m_Parent;
		}
		return entity;
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		NetPrefab netPrefab = GetNetPrefab();
		m_Prefab = null;
		if (actualMode == Mode.Replace)
		{
			if (netPrefab != null)
			{
				if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(netPrefab, out var component))
				{
					if ((component.m_PlacementFlags & Game.Net.PlacementFlags.UndergroundUpgrade) == 0)
					{
						if (component.m_ElevationRange.min >= 0f && component.m_UndergroundPrefab == Entity.Null)
						{
							underground = false;
						}
						else if (component.m_ElevationRange.max < 0f && component.m_UndergroundPrefab == Entity.Null)
						{
							underground = true;
						}
					}
				}
				else
				{
					underground = false;
				}
				m_Prefab = ((underground && component.m_UndergroundPrefab != Entity.Null) ? m_PrefabSystem.GetPrefab<NetPrefab>(component.m_UndergroundPrefab) : netPrefab);
				NetData componentData = m_PrefabSystem.GetComponentData<NetData>(m_Prefab);
				m_PrefabSystem.TryGetComponentData<NetGeometryData>(m_Prefab, out var component2);
				if (underground)
				{
					m_ToolRaycastSystem.collisionMask = CollisionMask.Underground;
				}
				else
				{
					m_ToolRaycastSystem.collisionMask = CollisionMask.OnGround | CollisionMask.Overground;
				}
				if ((component2.m_Flags & Game.Net.GeometryFlags.Marker) != 0)
				{
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Markers;
				}
				m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubElements | RaycastFlags.IgnoreSecondary;
				m_ToolRaycastSystem.typeMask = TypeMask.Net;
				m_ToolRaycastSystem.netLayerMask = componentData.m_RequiredLayers;
			}
			else
			{
				m_ToolRaycastSystem.collisionMask = (CollisionMask)0;
				m_ToolRaycastSystem.typeMask = TypeMask.Net;
				m_ToolRaycastSystem.netLayerMask = Layer.None;
			}
		}
		else if (netPrefab != null)
		{
			if (InputManager.instance.activeControlScheme == InputManager.ControlScheme.KeyboardAndMouse && m_State == State.Applying && SharedSettings.instance.input.elevationDraggingEnabled)
			{
				Camera main = Camera.main;
				if (main != null && InputManager.instance.mouseOnScreen)
				{
					Line3 line = ToolRaycastSystem.CalculateRaycastLine(main);
					float3 hitPosition = m_ApplyStartPoint.m_HitPosition;
					hitPosition.y += m_ApplyStartPoint.m_Elevation;
					if (TryIntersectLineWithPlane(plane: new Triangle3(hitPosition, hitPosition + math.up(), hitPosition + (float3)main.transform.right), line: line, minDot: 0.05f, d: out var d) && d >= 0f && (double)d <= 1.0)
					{
						float3 y = MathUtils.Position(line, d);
						float num = y.y - hitPosition.y;
						float num2 = math.distance(line.a, y);
						float y2 = 2f * math.tan(math.radians(math.min(89f, main.fieldOfView * 0.5f))) * num2;
						float num3 = math.abs(num) / math.max(1f, y2);
						float num4 = 0.5f / (1f + num3 * 20f);
						if (m_ApplyTimer >= num4)
						{
							GetSurfaceHeights(netPrefab, out var overground, out var num5);
							bool flag = m_ApplyStartPoint.m_Elevation < 0f;
							float num6 = math.select(overground, num5, flag);
							elevation = m_ApplyStartPoint.m_Elevation + num - num6;
							elevation = math.round(elevation / elevationStep) * elevationStep;
							bool flag2 = elevation < 0f;
							if (overground != num5 && flag2 != flag)
							{
								num6 = math.select(overground, num5, flag2);
								elevation = m_ApplyStartPoint.m_Elevation + num - num6;
								elevation = math.round(elevation / elevationStep) * elevationStep;
								bool flag3 = elevation < 0f;
								if (flag3 != flag2)
								{
									elevation = math.select(0f, 0f - elevationStep, flag3);
								}
							}
							if (elevation > m_LastMouseElevation)
							{
								m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetElevationUpSound);
							}
							else if (elevation < m_LastMouseElevation)
							{
								m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetElevationDownSound);
							}
							m_LastMouseElevation = elevation;
						}
					}
				}
				m_ApplyTimer += UnityEngine.Time.deltaTime;
			}
			m_Prefab = netPrefab;
			if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(netPrefab, out var component3) && component3.m_UndergroundPrefab != Entity.Null && elevation < 0f)
			{
				m_Prefab = m_PrefabSystem.GetPrefab<NetPrefab>(component3.m_UndergroundPrefab);
			}
			if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out component3))
			{
				CheckElevationRange(component3);
				elevation = MathUtils.Clamp(elevation, component3.m_ElevationRange);
			}
			else
			{
				m_LastElevationRange = default(Bounds1);
				elevation = 0f;
			}
			NetData componentData2 = m_PrefabSystem.GetComponentData<NetData>(m_Prefab);
			m_PrefabSystem.TryGetComponentData<NetGeometryData>(m_Prefab, out var component4);
			if (elevation < 0f)
			{
				m_ToolRaycastSystem.collisionMask = CollisionMask.Underground;
				m_ToolRaycastSystem.typeMask = TypeMask.Terrain;
			}
			else
			{
				m_ToolRaycastSystem.collisionMask = CollisionMask.OnGround | CollisionMask.Overground;
				m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Water;
			}
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.ElevateOffset | RaycastFlags.SubElements | RaycastFlags.Outside | RaycastFlags.IgnoreSecondary;
			m_ToolRaycastSystem.netLayerMask = componentData2.m_ConnectLayers;
			m_ToolRaycastSystem.rayOffset = new float3(0f, 0f - component4.m_DefaultSurfaceHeight.max - elevation, 0f);
			GetAvailableSnapMask(out var onMask, out var offMask);
			Snap actualSnap = ToolBaseSystem.GetActualSnap(selectedSnap, onMask, offMask);
			if ((actualSnap & (Snap.ExistingGeometry | Snap.NearbyGeometry)) != Snap.None)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.Net;
				if ((component4.m_Flags & Game.Net.GeometryFlags.Marker) != 0)
				{
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Markers;
				}
			}
			if ((actualSnap & Snap.ObjectSurface) != Snap.None)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.StaticObjects;
				if (m_ToolSystem.actionMode.IsEditor())
				{
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Placeholders;
				}
			}
		}
		else
		{
			m_ToolRaycastSystem.collisionMask = (CollisionMask)0;
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.ElevateOffset | RaycastFlags.SubElements | RaycastFlags.Outside;
			m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Net | TypeMask.Water;
			m_ToolRaycastSystem.netLayerMask = Layer.None;
			m_ToolRaycastSystem.rayOffset = default(float3);
		}
		if (m_ToolSystem.actionMode.IsEditor())
		{
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubElements | RaycastFlags.UpgradeIsMain;
		}
	}
```

- `private static IsNearEnd(Unity.Entities.Entity edge, Game.Net.Curve curve, Unity.Mathematics.float3 position, System.Boolean invert, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeGeometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeGeometryData) : System.Boolean`  

```csharp
private static bool IsNearEnd(Entity edge, Curve curve, float3 position, bool invert, ref ComponentLookup<EdgeGeometry> edgeGeometryData)
	{
		if (edgeGeometryData.TryGetComponent(edge, out var componentData))
		{
			Bezier4x3 bezier4x = MathUtils.Lerp(componentData.m_Start.m_Left, componentData.m_Start.m_Right, 0.5f);
			Bezier4x3 bezier4x2 = MathUtils.Lerp(componentData.m_End.m_Left, componentData.m_End.m_Right, 0.5f);
			float t;
			float num = MathUtils.Distance(bezier4x.xz, position.xz, out t);
			float t2;
			float num2 = MathUtils.Distance(bezier4x2.xz, position.xz, out t2);
			float middleLength = componentData.m_Start.middleLength;
			float middleLength2 = componentData.m_End.middleLength;
			return math.select(t * middleLength, middleLength + t2 * middleLength2, num2 < num) > (middleLength + middleLength2) * 0.5f != invert;
		}
		MathUtils.Distance(curve.m_Bezier.xz, position.xz, out var t3);
		return t3 > 0.5f;
	}
```

- `private LoadToolPreferences() : System.Void`  

```csharp
private void LoadToolPreferences()
	{
		PrefabBase prefabBase = GetPrefab();
		if (!(prefabBase == null))
		{
			m_LoadingPreferences = true;
			Entity entity = m_PrefabSystem.GetEntity(prefabBase);
			base.EntityManager.TryGetComponent<UIObjectData>(entity, out var component);
			if (m_ToolPreferences.TryGetValue(component.m_Group, out var value))
			{
				value.Load(this);
			}
			else
			{
				m_DefaultToolPreferences.Load(this);
			}
			m_LoadingPreferences = false;
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_ZoneSearchSystem = base.World.GetOrCreateSystemManaged<Game.Zones.SearchSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_NetInitializeSystem = base.World.GetOrCreateSystemManaged<NetInitializeSystem>();
		m_ControlPoints = new NativeList<ControlPoint>(4, Allocator.Persistent);
		m_SnapLines = new NativeList<SnapLine>(10, Allocator.Persistent);
		m_UpgradeStates = new NativeList<UpgradeState>(4, Allocator.Persistent);
		m_StartEntity = new NativeReference<Entity>(Allocator.Persistent);
		m_LastSnappedEntity = new NativeReference<Entity>(Allocator.Persistent);
		m_LastControlPointsAngle = new NativeReference<int>(Allocator.Persistent);
		m_AppliedUpgrade = new NativeReference<AppliedUpgrade>(Allocator.Persistent);
		m_DefinitionQuery = GetDefinitionQuery();
		m_ContainerQuery = GetContainerQuery();
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Lane>());
		m_EdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Edge>());
		m_NodeQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Game.Net.Node>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_DowngradeNetEdge = InputManager.instance.toolActionCollection.GetActionState("Downgrade Net Edge", "NetToolSystem");
		m_PlaceNetControlPoint = InputManager.instance.toolActionCollection.GetActionState("Place Net Control Point", "NetToolSystem");
		m_PlaceNetEdge = InputManager.instance.toolActionCollection.GetActionState("Place Net Edge", "NetToolSystem");
		m_PlaceNetNode = InputManager.instance.toolActionCollection.GetActionState("Place Net Node", "NetToolSystem");
		m_ReplaceNetEdge = InputManager.instance.toolActionCollection.GetActionState("Replace Net Edge", "NetToolSystem");
		m_UndoNetControlPoint = InputManager.instance.toolActionCollection.GetActionState("Undo Net Control Point", "NetToolSystem");
		m_UpgradeNetEdge = InputManager.instance.toolActionCollection.GetActionState("Upgrade Net Edge", "NetToolSystem");
		m_DiscardUpgrade = InputManager.instance.toolActionCollection.GetActionState("Discard Upgrade", "NetToolSystem");
		m_DiscardDowngrade = InputManager.instance.toolActionCollection.GetActionState("Discard Downgrade", "NetToolSystem");
		m_DiscardReplace = InputManager.instance.toolActionCollection.GetActionState("Discard Replace", "NetToolSystem");
		elevationStep = 10f;
		parallelOffset = 8f;
		selectedSnap &= ~(Snap.AutoParent | Snap.ContourLines);
		m_DefaultToolPreferences = new NetToolPreferences();
		m_DefaultToolPreferences.Save(this);
		m_ToolPreferences = new Dictionary<Entity, NetToolPreferences>();
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_ControlPoints.Dispose();
		m_SnapLines.Dispose();
		m_UpgradeStates.Dispose();
		m_StartEntity.Dispose();
		m_LastSnappedEntity.Dispose();
		m_LastControlPointsAngle.Dispose();
		m_AppliedUpgrade.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		ResetToolPreferences();
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_ControlPoints.Clear();
		m_SnapLines.Clear();
		m_UpgradeStates.Clear();
		m_StartEntity.Value = default(Entity);
		m_LastSnappedEntity.Value = default(Entity);
		m_LastControlPointsAngle.Value = 0;
		m_AppliedUpgrade.Value = default(AppliedUpgrade);
		m_LastRaycastPoint = default(ControlPoint);
		m_ApplyStartPoint = default(ControlPoint);
		m_State = State.Default;
		m_ApplyTimer = 0f;
		m_RandomSeed = RandomSeed.Next();
		m_ForceCancel = false;
		m_ApplyBlocked = false;
		base.requireZones = false;
		base.requireUnderground = false;
		base.requirePipelines = false;
		base.requireNetArrows = false;
		base.requireAreas = AreaTypeMask.None;
		base.requireNet = Layer.None;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		UpdateActions();
		if (m_FocusChanged)
		{
			return inputDeps;
		}
		Mode mode = actualMode;
		if (mode != m_LastActualMode)
		{
			if (m_LastActualMode == Mode.Replace || mode == Mode.Replace)
			{
				m_ControlPoints.Clear();
				m_State = State.Default;
			}
			else
			{
				int maxControlPointCount = GetMaxControlPointCount(mode);
				if (maxControlPointCount < m_ControlPoints.Length)
				{
					m_ControlPoints.RemoveRange(maxControlPointCount, m_ControlPoints.Length - maxControlPointCount);
				}
			}
			m_LastActualMode = mode;
		}
		bool flag = m_ForceCancel;
		m_ForceCancel = false;
		if (mode != Mode.Replace)
		{
			inputDeps = UpdateStartEntity(inputDeps);
		}
		if (m_Prefab != null)
		{
			NetData componentData = m_PrefabSystem.GetComponentData<NetData>(m_Prefab);
			m_PrefabSystem.TryGetComponentData<NetGeometryData>(m_Prefab, out var component);
			bool laneContainer = m_PrefabSystem.HasComponent<EditorContainerData>(m_Prefab);
			base.requireZones = false;
			base.requireUnderground = underground;
			base.requirePipelines = false;
			base.requireNetArrows = (component.m_Flags & Game.Net.GeometryFlags.Directional) != 0;
			base.requireAreas = AreaTypeMask.None;
			base.requireNet = componentData.m_ConnectLayers | componentData.m_RequiredLayers | component.m_MergeLayers | component.m_IntersectLayers;
			if (actualMode != Mode.Replace)
			{
				base.requireUnderground = elevation < 0f && (elevation <= component.m_ElevationLimit * -3f || (component.m_Flags & Game.Net.GeometryFlags.LoweredIsTunnel) != 0);
				base.requirePipelines = elevation < 0f;
			}
			if (m_PrefabSystem.TryGetComponentData<PlaceableNetData>(m_Prefab, out var component2))
			{
				if ((component2.m_PlacementFlags & Game.Net.PlacementFlags.OnGround) != Game.Net.PlacementFlags.None && !base.requireUnderground)
				{
					base.requireZones = true;
					base.requireAreas |= AreaTypeMask.Lots;
					if (m_ToolSystem.actionMode.IsEditor())
					{
						base.requireAreas |= AreaTypeMask.Spaces;
					}
				}
				if (mode != Mode.Replace && (component2.m_ElevationRange.max > 0f || (component.m_Flags & Game.Net.GeometryFlags.RequireElevated) != 0) && !base.requireUnderground)
				{
					base.requireNet |= Layer.Waterway;
				}
			}
			UpdateInfoview(m_ToolSystem.actionMode.IsEditor() ? Entity.Null : m_PrefabSystem.GetEntity(m_Prefab));
			GetAvailableSnapMask(component, component2, mode, m_ToolSystem.actionMode.IsEditor(), laneContainer, base.requireUnderground, out m_SnapOnMask, out m_SnapOffMask);
			if (m_State != State.Default && !base.applyAction.enabled && !base.secondaryApplyAction.enabled)
			{
				m_State = State.Default;
			}
			if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
			{
				if (actualMode == Mode.Replace)
				{
					switch (m_State)
					{
					case State.Default:
						if (m_ApplyBlocked)
						{
							if (base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
							{
								m_ApplyBlocked = false;
							}
							return Update(inputDeps, fullUpdate: false);
						}
						if (base.applyAction.WasPressedThisFrame())
						{
							return Apply(inputDeps, base.applyAction.WasReleasedThisFrame());
						}
						if (base.secondaryApplyAction.WasPressedThisFrame())
						{
							return Cancel(inputDeps, base.secondaryApplyAction.WasReleasedThisFrame());
						}
						return Update(inputDeps, fullUpdate: false);
					case State.Applying:
						if (base.cancelAction.WasPressedThisFrame())
						{
							m_ApplyBlocked = true;
							m_State = State.Default;
							return Update(inputDeps, fullUpdate: true);
						}
						if (base.applyAction.WasReleasedThisFrame())
						{
							return Apply(inputDeps);
						}
						return Update(inputDeps, fullUpdate: false);
					case State.Cancelling:
						if (base.cancelAction.WasPressedThisFrame())
						{
							m_ApplyBlocked = true;
							m_State = State.Default;
							return Update(inputDeps, fullUpdate: true);
						}
						if (base.secondaryApplyAction.WasReleasedThisFrame())
						{
							return Cancel(inputDeps);
						}
						return Update(inputDeps, fullUpdate: false);
					default:
						return Update(inputDeps, fullUpdate: false);
					}
				}
				if (m_State != State.Cancelling && base.cancelAction.WasPressedThisFrame())
				{
					return Cancel(inputDeps, base.cancelAction.WasReleasedThisFrame());
				}
				if (m_State == State.Cancelling && (flag || base.cancelAction.WasReleasedThisFrame()))
				{
					return Cancel(inputDeps);
				}
				if (m_State != State.Applying && base.applyAction.WasPressedThisFrame())
				{
					return Apply(inputDeps, base.applyAction.WasReleasedThisFrame());
				}
				if (m_State == State.Applying && base.applyAction.WasReleasedThisFrame())
				{
					return Apply(inputDeps);
				}
				return Update(inputDeps, fullUpdate: false);
			}
		}
		else
		{
			base.requireZones = false;
			base.requireUnderground = false;
			base.requirePipelines = false;
			base.requireNetArrows = false;
			base.requireAreas = AreaTypeMask.None;
			base.requireNet = Layer.None;
			UpdateInfoview(Entity.Null);
		}
		if (m_State == State.Applying && (base.applyAction.WasReleasedThisFrame() || base.cancelAction.WasPressedThisFrame()))
		{
			m_State = State.Default;
		}
		else if (m_State == State.Cancelling && (base.secondaryApplyAction.WasReleasedThisFrame() || base.cancelAction.WasPressedThisFrame()))
		{
			m_State = State.Default;
		}
		return Clear(inputDeps);
	}
```

- `public ResetToolPreferences() : System.Void`  

```csharp
public void ResetToolPreferences()
	{
		m_ToolPreferences.Clear();
		m_DefaultToolPreferences.Load(this);
	}
```

- `private SaveToolPreferences() : System.Void`  

```csharp
private void SaveToolPreferences()
	{
		if (m_LoadingPreferences)
		{
			return;
		}
		PrefabBase prefabBase = GetPrefab();
		if (!(prefabBase == null))
		{
			Entity entity = m_PrefabSystem.GetEntity(prefabBase);
			base.EntityManager.TryGetComponent<UIObjectData>(entity, out var component);
			if (!m_ToolPreferences.ContainsKey(component.m_Group))
			{
				m_ToolPreferences[component.m_Group] = new NetToolPreferences();
			}
			m_ToolPreferences[component.m_Group].Save(this);
		}
	}
```

- `private SetAppliedUpgrade(System.Boolean removing) : System.Void`  

```csharp
private void SetAppliedUpgrade(bool removing)
	{
		m_AppliedUpgrade.Value = default(AppliedUpgrade);
		if (m_UpgradeStates.Length < 1 || m_ControlPoints.Length < 4)
		{
			return;
		}
		Entity originalEntity = m_ControlPoints[m_ControlPoints.Length - 3].m_OriginalEntity;
		Entity originalEntity2 = m_ControlPoints[m_ControlPoints.Length - 2].m_OriginalEntity;
		UpgradeState upgradeState = m_UpgradeStates[m_UpgradeStates.Length - 1];
		AppliedUpgrade value = new AppliedUpgrade
		{
			m_SubReplacementPrefab = upgradeState.m_SubReplacementPrefab,
			m_Flags = (removing ? upgradeState.m_RemoveFlags : upgradeState.m_AddFlags),
			m_SubReplacementType = upgradeState.m_SubReplacementType,
			m_SubReplacementSide = upgradeState.m_SubReplacementSide
		};
		if (originalEntity == originalEntity2)
		{
			value.m_Entity = originalEntity;
			m_AppliedUpgrade.Value = value;
		}
		else
		{
			if (!base.EntityManager.TryGetBuffer(originalEntity, isReadOnly: true, out DynamicBuffer<ConnectedEdge> buffer))
			{
				return;
			}
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity edge = buffer[i].m_Edge;
				if (base.EntityManager.TryGetComponent<Edge>(edge, out var component) && ((component.m_Start == originalEntity && component.m_End == originalEntity2) || (component.m_End == originalEntity && component.m_Start == originalEntity2)))
				{
					value.m_Entity = edge;
					m_AppliedUpgrade.Value = value;
				}
			}
		}
	}
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public override void SetUnderground(bool underground)
	{
		if (actualMode == Mode.Replace)
		{
			this.underground = underground;
		}
	}
```

- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle SnapControlPoints(JobHandle inputDeps, bool removeUpgrade)
	{
		Entity lanePrefab = Entity.Null;
		Entity serviceUpgradeOwner = Entity.Null;
		if (m_LanePrefab != null)
		{
			lanePrefab = m_PrefabSystem.GetEntity(m_LanePrefab);
		}
		if (serviceUpgrade)
		{
			serviceUpgradeOwner = GetUpgradable(m_ToolSystem.selected);
		}
		JobHandle deps;
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle deps2;
		SnapJob jobData = new SnapJob
		{
			m_Mode = actualMode,
			m_Snap = GetActualSnap(),
			m_Elevation = elevation,
			m_Prefab = m_PrefabSystem.GetEntity(m_Prefab),
			m_LanePrefab = lanePrefab,
			m_ServiceUpgradeOwner = serviceUpgradeOwner,
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_RemoveUpgrade = removeUpgrade,
			m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneBlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AssetStampData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AssetStampData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubReplacements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_ZoneCells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabCompositionAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies2),
			m_ZoneSearchTree = m_ZoneSearchSystem.GetSearchTree(readOnly: true, out dependencies3),
			m_ControlPoints = m_ControlPoints,
			m_SnapLines = m_SnapLines,
			m_UpgradeStates = m_UpgradeStates,
			m_StartEntity = m_StartEntity,
			m_AppliedUpgrade = m_AppliedUpgrade,
			m_LastSnappedEntity = m_LastSnappedEntity,
			m_LastControlPointsAngle = m_LastControlPointsAngle,
			m_SourceUpdateData = m_AudioManager.GetSourceUpdateData(out deps2)
		};
		inputDeps = JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2);
		inputDeps = JobHandle.CombineDependencies(inputDeps, dependencies3, deps);
		inputDeps = JobHandle.CombineDependencies(inputDeps, deps2);
		JobHandle jobHandle = IJobExtensions.Schedule(jobData, inputDeps);
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		return jobHandle;
	}
```

- `private static TryIntersectLineWithPlane(Colossal.Mathematics.Line3 line, Colossal.Mathematics.Triangle3 plane, System.Single minDot, System.Single& d) : System.Boolean`  

```csharp
private static bool TryIntersectLineWithPlane(Line3 line, Triangle3 plane, float minDot, out float d)
	{
		float3 x = math.normalize(MathUtils.NormalCW(plane));
		if (math.abs(math.dot(x, math.normalize(line.ab))) > minDot)
		{
			float3 y = line.a - plane.a;
			d = (0f - math.dot(x, y)) / math.dot(x, line.ab);
			return true;
		}
		d = 0f;
		return false;
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		if (prefab is NetPrefab netPrefab)
		{
			this.prefab = netPrefab;
			return true;
		}
		if (prefab is NetLanePrefab netLanePrefab)
		{
			lane = netLanePrefab;
			return true;
		}
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps, bool fullUpdate)
	{
		if (actualMode == Mode.Replace)
		{
			if (GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate))
			{
				controlPoint.m_Elevation = elevation;
				fullUpdate = fullUpdate || forceUpdate;
				if (m_ControlPoints.Length == 0)
				{
					base.applyMode = ApplyMode.Clear;
					m_ControlPoints.Add(in controlPoint);
					inputDeps = SnapControlPoints(inputDeps, m_State == State.Cancelling);
					inputDeps = UpdateCourse(inputDeps, m_State == State.Cancelling);
				}
				else
				{
					base.applyMode = ApplyMode.None;
					if (fullUpdate || !m_LastRaycastPoint.Equals(controlPoint))
					{
						m_LastRaycastPoint = controlPoint;
						ControlPoint controlPoint2 = m_ControlPoints[m_ControlPoints.Length - 1];
						if (m_State == State.Applying || m_State == State.Cancelling)
						{
							if (m_ControlPoints.Length == 1)
							{
								m_ControlPoints.Add(in controlPoint);
							}
							else
							{
								m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint;
							}
						}
						else
						{
							m_ControlPoints.Clear();
							m_UpgradeStates.Clear();
							m_ControlPoints.Add(in controlPoint);
						}
						inputDeps = SnapControlPoints(inputDeps, m_State == State.Cancelling);
						JobHandle.ScheduleBatchedJobs();
						if (!fullUpdate)
						{
							inputDeps.Complete();
							ControlPoint other = m_ControlPoints[m_ControlPoints.Length - 1];
							fullUpdate = !controlPoint2.EqualsIgnoreHit(other);
						}
						if (fullUpdate)
						{
							base.applyMode = ApplyMode.Clear;
							inputDeps = UpdateCourse(inputDeps, m_State == State.Cancelling);
						}
					}
				}
			}
			else
			{
				if (m_State == State.Default)
				{
					m_ControlPoints.Clear();
					m_UpgradeStates.Clear();
					m_AppliedUpgrade.Value = default(AppliedUpgrade);
				}
				base.applyMode = ApplyMode.Clear;
				inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
			}
			return inputDeps;
		}
		if (GetRaycastResult(out ControlPoint controlPoint3, out bool forceUpdate2))
		{
			if (m_State == State.Applying)
			{
				controlPoint3 = m_ApplyStartPoint;
			}
			controlPoint3.m_HitPosition.y += elevation;
			controlPoint3.m_Elevation = elevation;
			fullUpdate = fullUpdate || forceUpdate2;
			if (m_ControlPoints.Length == 0)
			{
				base.applyMode = ApplyMode.Clear;
				m_ControlPoints.Add(in controlPoint3);
				inputDeps = SnapControlPoints(inputDeps, removeUpgrade: false);
				inputDeps = UpdateCourse(inputDeps, removeUpgrade: false);
			}
			else
			{
				base.applyMode = ApplyMode.None;
				if (fullUpdate || !m_LastRaycastPoint.Equals(controlPoint3))
				{
					if (m_ControlPoints.Length >= 2 && math.distance(m_LastRaycastPoint.m_Position, controlPoint3.m_Position) > 0.01f)
					{
						m_AudioManager.PlayUISoundIfNotPlaying(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetExpandSound);
					}
					m_LastRaycastPoint = controlPoint3;
					ControlPoint controlPoint4 = m_ControlPoints[m_ControlPoints.Length - 1];
					m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint3;
					inputDeps = SnapControlPoints(inputDeps, removeUpgrade: false);
					JobHandle.ScheduleBatchedJobs();
					if (!fullUpdate)
					{
						inputDeps.Complete();
						ControlPoint other2 = m_ControlPoints[m_ControlPoints.Length - 1];
						fullUpdate = !controlPoint4.EqualsIgnoreHit(other2);
					}
					if (fullUpdate)
					{
						base.applyMode = ApplyMode.Clear;
						inputDeps = UpdateCourse(inputDeps, removeUpgrade: false);
					}
				}
			}
		}
		else
		{
			base.applyMode = ApplyMode.Clear;
			inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		}
		return inputDeps;
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		using (ProxyAction.DeferStateUpdating())
		{
			switch (actualMode)
			{
			case Mode.Straight:
			case Mode.SimpleCurve:
			case Mode.ComplexCurve:
			case Mode.Continuous:
			case Mode.Grid:
			{
				int maxControlPointCount = GetMaxControlPointCount(actualMode);
				base.applyAction.enabled = base.actionsEnabled && ((m_ControlPoints.Length > 1 && m_ControlPoints.Length < maxControlPointCount) || GetAllowApply());
				base.applyActionOverride = ((m_ControlPoints.Length < maxControlPointCount) ? m_PlaceNetControlPoint : m_PlaceNetEdge);
				base.secondaryApplyAction.enabled = false;
				base.secondaryApplyActionOverride = null;
				base.cancelAction.enabled = base.actionsEnabled && m_ControlPoints.Length >= 2;
				base.cancelActionOverride = m_UndoNetControlPoint;
				break;
			}
			case Mode.Replace:
			{
				bool flag = m_ControlPoints.Length > 4;
				if (prefab.Has<NetUpgrade>())
				{
					if (!flag)
					{
						base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
						base.applyActionOverride = m_UpgradeNetEdge;
						base.secondaryApplyAction.enabled = base.actionsEnabled;
						base.secondaryApplyActionOverride = m_DowngradeNetEdge;
						base.cancelAction.enabled = false;
						base.cancelActionOverride = null;
					}
					else if (m_State == State.Applying)
					{
						base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
						base.applyActionOverride = m_UpgradeNetEdge;
						base.secondaryApplyAction.enabled = false;
						base.secondaryApplyActionOverride = null;
						base.cancelAction.enabled = base.actionsEnabled;
						base.cancelActionOverride = m_DiscardUpgrade;
					}
					else if (m_State == State.Cancelling)
					{
						base.applyAction.enabled = false;
						base.applyActionOverride = null;
						base.secondaryApplyAction.enabled = base.actionsEnabled;
						base.secondaryApplyActionOverride = m_DowngradeNetEdge;
						base.cancelAction.enabled = base.actionsEnabled;
						base.cancelActionOverride = m_DiscardDowngrade;
					}
				}
				else
				{
					base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
					base.applyActionOverride = m_ReplaceNetEdge;
					base.secondaryApplyAction.enabled = false;
					base.secondaryApplyActionOverride = null;
					if (flag)
					{
						base.cancelAction.enabled = base.actionsEnabled;
						base.cancelActionOverride = m_DiscardReplace;
					}
					else
					{
						base.cancelAction.enabled = false;
						base.cancelActionOverride = null;
					}
				}
				break;
			}
			case Mode.Point:
				base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
				base.applyActionOverride = m_PlaceNetNode;
				base.secondaryApplyAction.enabled = false;
				base.secondaryApplyActionOverride = null;
				base.cancelAction.enabled = base.actionsEnabled && m_ControlPoints.Length >= 2;
				base.cancelActionOverride = m_UndoNetControlPoint;
				break;
			}
		}
	}
```

- `private UpdateCourse(Unity.Jobs.JobHandle inputDeps, System.Boolean removeUpgrade) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateCourse(JobHandle inputDeps, bool removeUpgrade)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		if (m_Prefab != null)
		{
			JobHandle deps;
			CreateDefinitionsJob jobData = new CreateDefinitionsJob
			{
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_RemoveUpgrade = removeUpgrade,
				m_LefthandTraffic = m_CityConfigurationSystem.leftHandTraffic,
				m_Mode = actualMode,
				m_ParallelCount = math.select(new int2(actualParallelCount, 0), new int2(0, actualParallelCount), m_CityConfigurationSystem.leftHandTraffic),
				m_ParallelOffset = parallelOffset,
				m_RandomSeed = m_RandomSeed,
				m_ControlPoints = m_ControlPoints,
				m_UpgradeStates = m_UpgradeStates,
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FixedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Extension_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PlaceableData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubReplacements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_CachedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_LocalNodeCache_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubAreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubAreaNode_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabPlaceholderElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_NetPrefab = m_PrefabSystem.GetEntity(m_Prefab),
				m_WaterSurfaceData = m_WaterSystem.GetVelocitiesSurfaceData(out deps),
				m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
			};
			if (m_LanePrefab != null)
			{
				jobData.m_LanePrefab = m_PrefabSystem.GetEntity(m_LanePrefab);
			}
			if (serviceUpgrade)
			{
				jobData.m_ServiceUpgradeOwner = GetUpgradable(m_ToolSystem.selected);
			}
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(inputDeps, deps));
			m_WaterSystem.AddVelocitySurfaceReader(jobHandle2);
			m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		return jobHandle;
	}
```

- `private UpdateStartEntity(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateStartEntity(JobHandle inputDeps)
	{
		if (!m_DefinitionQuery.IsEmptyIgnoreFilter)
		{
			return JobChunkExtensions.Schedule(new UpdateStartEntityJob
			{
				m_NetCourseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_NetCourse_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StartEntity = m_StartEntity
			}, m_DefinitionQuery, inputDeps);
		}
		return inputDeps;
	}
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

