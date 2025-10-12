# Game.Tools.BulldozeToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.BulldozeToolSystem+Mode <mode>k__BackingField`  
- `private System.Boolean <underground>k__BackingField`  
- `private System.Boolean <allowManipulation>k__BackingField`  
- `private System.Boolean <debugBypassBulldozeConfirmation>k__BackingField`  
- `private Game.Prefabs.BulldozePrefab <prefab>k__BackingField`  
- `public System.Action EventConfirmationRequested`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_RoadQuery`  
- `private Unity.Entities.EntityQuery m_PlantQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Game.Tools.ControlPoint m_LastRaycastPoint`  
- `private Game.Tools.BulldozeToolSystem+State m_State`  
- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  
- `private Game.Input.IProxyAction m_Bulldoze`  
- `private Game.Input.IProxyAction m_BulldozeDiscard`  
- `private System.Boolean m_ApplyBlocked`  
- `private Game.Tools.BulldozeToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public System.Int32 uiModeIndex { get }`  
- `public System.Boolean allowUnderground { get }`  
- `public Game.Tools.BulldozeToolSystem+Mode mode { get; set }`  
- `public Game.Tools.BulldozeToolSystem+Mode actualMode { get }`  
- `public System.Boolean underground { get; set }`  
- `public System.Boolean allowManipulation { get; set }`  
- `public System.Boolean debugBypassBulldozeConfirmation { get; set }`  
- `public Game.Prefabs.BulldozePrefab prefab { get; set }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

## Constructors

- `public BulldozeToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public ConfirmAction(System.Boolean confirm) : System.Void`  
- `private ConfirmationNeeded() : System.Boolean`  
- `public virtual ElevationDown() : System.Void`  
- `public virtual ElevationScroll() : System.Void`  
- `public virtual ElevationUp() : System.Void`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  
- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  
- `public virtual InitializeRaycast() : System.Void`  
- `private IsMultiSelection() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual SetUnderground(System.Boolean underground) : System.Void`  
- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.BulldozeToolSystem+Mode`  
- `Game.Tools.BulldozeToolSystem+State`  
- `Game.Tools.BulldozeToolSystem+PathEdge`  
- `Game.Tools.BulldozeToolSystem+PathItem`  
- `Game.Tools.BulldozeToolSystem+SnapJob`  
- `Game.Tools.BulldozeToolSystem+CreateDefinitionsJob`  
- `Game.Tools.BulldozeToolSystem+TypeHandle`  
- `Game.Tools.BulldozeToolSystem+<get_toolActions>d__47`  

