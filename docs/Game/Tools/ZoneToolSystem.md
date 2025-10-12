# Game.Tools.ZoneToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ZoneToolSystem+Mode <mode>k__BackingField`  
- `private Game.Prefabs.ZonePrefab m_Prefab`  
- `private System.Boolean <overwrite>k__BackingField`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_DefinitionGroup`  
- `private Unity.Entities.EntityQuery m_TempBlockQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Game.Input.IProxyAction m_ApplyZone`  
- `private Game.Input.IProxyAction m_RemoveZone`  
- `private Game.Input.IProxyAction m_DiscardZoning`  
- `private Game.Input.IProxyAction m_DiscardDezoning`  
- `private Game.Input.IProxyAction m_DefaultDiscardApply`  
- `private Game.Input.IProxyAction m_DefaultDiscardRemove`  
- `private System.Boolean m_ApplyBlocked`  
- `private Game.Tools.ControlPoint m_RaycastPoint`  
- `private Game.Tools.ControlPoint m_StartPoint`  
- `private Colossal.Collections.NativeValue<Game.Tools.ControlPoint> m_SnapPoint`  
- `private Game.Tools.ZoneToolSystem+State m_State`  
- `private Game.Tools.ZoneToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public System.Int32 uiModeIndex { get }`  
- `public Game.Tools.ZoneToolSystem+Mode mode { get; set }`  
- `public Game.Prefabs.ZonePrefab prefab { get; set }`  
- `public System.Boolean overwrite { get; set }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

## Constructors

- `public ZoneToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `protected GetAllowApplyZone() : System.Boolean`  
- `protected GetAllowRemoveZone() : System.Boolean`  
- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private SetZoneType(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private SnapPoint(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.ZoneToolSystem+Mode`  
- `Game.Tools.ZoneToolSystem+State`  
- `Game.Tools.ZoneToolSystem+SetZoneTypeJob`  
- `Game.Tools.ZoneToolSystem+SnapJob`  
- `Game.Tools.ZoneToolSystem+CreateDefinitionsJob`  
- `Game.Tools.ZoneToolSystem+TypeHandle`  
- `Game.Tools.ZoneToolSystem+<get_toolActions>d__34`  

