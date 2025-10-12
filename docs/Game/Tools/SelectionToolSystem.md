# Game.Tools.SelectionToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.SelectionType <selectionType>k__BackingField`  
- `private Unity.Entities.Entity <selectionOwner>k__BackingField`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Areas.MapTileSystem m_MapTileSystem`  
- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_DefinitionGroup`  
- `private Unity.Entities.EntityQuery m_TempGroup`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Unity.Entities.Entity m_SelectionEntity`  
- `private Unity.Entities.Entity m_LastOwner`  
- `private Game.Tools.SelectionType m_LastType`  
- `private Unity.Entities.EntityArchetype m_SelectionArchetype`  
- `private Game.Tools.SelectionToolSystem+State m_State`  
- `private Game.Tools.ControlPoint m_StartPoint`  
- `private Game.Tools.ControlPoint m_RaycastPoint`  
- `private Game.Input.IProxyAction m_SelectArea`  
- `private Game.Input.IProxyAction m_DeselectArea`  
- `private Game.Input.IProxyAction m_DiscardSelect`  
- `private Game.Input.IProxyAction m_DiscardDeselect`  
- `private System.Boolean m_ApplyBlocked`  
- `private Game.Tools.SelectionToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public Game.Tools.SelectionType selectionType { get; set }`  
- `public Unity.Entities.Entity selectionOwner { get; set }`  
- `public Game.Tools.SelectionToolSystem+State state { get }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

## Constructors

- `public SelectionToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private CopySelection(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private CopyServiceDistricts(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private CopyStartTiles(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private GetAreaType(Game.Tools.SelectionType selectionType) : Game.Areas.AreaType`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  
- `public GetSelectionQuad(Colossal.Mathematics.Quad3& quad) : System.Boolean`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private ToggleTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean select) : Unity.Jobs.JobHandle`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private UpdateSelection(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private UpdateServiceDistricts(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private UpdateStartTiles(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.SelectionToolSystem+State`  
- `Game.Tools.SelectionToolSystem+FindEntitiesJob`  
- `Game.Tools.SelectionToolSystem+CreateDefinitionsJob`  
- `Game.Tools.SelectionToolSystem+ToggleEntityJob`  
- `Game.Tools.SelectionToolSystem+CopyStartTilesJob`  
- `Game.Tools.SelectionToolSystem+UpdateStartTilesJob`  
- `Game.Tools.SelectionToolSystem+CopyServiceDistrictsJob`  
- `Game.Tools.SelectionToolSystem+UpdateServiceDistrictsJob`  
- `Game.Tools.SelectionToolSystem+TypeHandle`  
- `Game.Tools.SelectionToolSystem+<get_toolActions>d__37`  

