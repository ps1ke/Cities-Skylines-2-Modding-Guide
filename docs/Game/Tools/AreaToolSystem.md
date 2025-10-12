# Game.Tools.AreaToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.AreaToolSystem+Mode <mode>k__BackingField`  
- `private Unity.Entities.Entity <recreate>k__BackingField`  
- `private System.Boolean <underground>k__BackingField`  
- `private System.Boolean <allowGenerate>k__BackingField`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Input.IProxyAction m_AddAreaNode`  
- `private Game.Input.IProxyAction m_InsertAreaNode`  
- `private Game.Input.IProxyAction m_MergeAreaNode`  
- `private Game.Input.IProxyAction m_MoveAreaNode`  
- `private Game.Input.IProxyAction m_DeleteAreaNode`  
- `private Game.Input.IProxyAction m_UndoAreaNode`  
- `private Game.Input.IProxyAction m_CompleteArea`  
- `private Game.Input.IProxyAction m_CreateArea`  
- `private Game.Input.IProxyAction m_DeleteArea`  
- `private Game.Input.IProxyAction m_DiscardInsertAreaNode`  
- `private Game.Input.IProxyAction m_DiscardMoveAreaNode`  
- `private Game.Input.IProxyAction m_DiscardMergeAreaNode`  
- `private Game.Input.IProxyAction m_CreateAreaOrMoveAreaNode`  
- `private Game.Input.IProxyAction m_CreateAreaOrInsertAreaNode`  
- `private System.Boolean m_ApplyBlocked`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_TempAreaQuery`  
- `private Unity.Entities.EntityQuery m_TempBuildingQuery`  
- `private Unity.Entities.EntityQuery m_MapTileQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Game.Tools.ControlPoint m_LastRaycastPoint`  
- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  
- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_MoveStartPositions`  
- `private Colossal.Collections.NativeValue<Game.Tools.AreaToolSystem+Tooltip> m_Tooltip`  
- `private Game.Tools.AreaToolSystem+Mode m_LastMode`  
- `private Game.Tools.AreaToolSystem+State m_State`  
- `private Game.Prefabs.AreaPrefab m_Prefab`  
- `private System.Boolean m_ControlPointsMoved`  
- `private System.Boolean m_AllowCreateArea`  
- `private System.Boolean m_ForceCancel`  
- `private Game.Tools.AreaToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public System.Int32 uiModeIndex { get }`  
- `public Game.Tools.AreaToolSystem+Mode mode { get; set }`  
- `public Game.Tools.AreaToolSystem+Mode actualMode { get }`  
- `public Unity.Entities.Entity recreate { get; set }`  
- `public System.Boolean underground { get; set }`  
- `public System.Boolean allowGenerate { get; private set }`  
- `public Game.Tools.AreaToolSystem+State state { get }`  
- `public Game.Tools.AreaToolSystem+Tooltip tooltip { get }`  
- `public Game.Prefabs.AreaPrefab prefab { get; set }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

## Constructors

- `public AreaToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual ElevationDown() : System.Void`  
- `public virtual ElevationScroll() : System.Void`  
- `public virtual ElevationUp() : System.Void`  
- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `private static GetAvailableSnapMask(Game.Prefabs.AreaGeometryData prefabAreaData, System.Boolean editorMode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `public GetControlPoints(Unity.Collections.NativeList`1[[Game.Tools.ControlPoint, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& moveStartPositions, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual SetUnderground(System.Boolean underground) : System.Void`  
- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas) : Unity.Jobs.JobHandle`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateApplyAction() : System.Void`  
- `private UpdateCancelAction() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempBuildings) : Unity.Jobs.JobHandle`  
- `private UpdateSecondaryApplyAction() : System.Void`  

## Nested types

- `Game.Tools.AreaToolSystem+Mode`  
- `Game.Tools.AreaToolSystem+State`  
- `Game.Tools.AreaToolSystem+Tooltip`  
- `Game.Tools.AreaToolSystem+SnapJob`  
- `Game.Tools.AreaToolSystem+RemoveMapTilesJob`  
- `Game.Tools.AreaToolSystem+CreateDefinitionsJob`  
- `Game.Tools.AreaToolSystem+TypeHandle`  
- `Game.Tools.AreaToolSystem+<get_toolActions>d__56`  

