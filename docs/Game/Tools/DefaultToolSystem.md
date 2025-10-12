# Game.Tools.DefaultToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <underground>k__BackingField`  
- `private System.Boolean <ignoreErrors>k__BackingField`  
- `private System.Boolean <allowManipulation>k__BackingField`  
- `private System.Boolean <debugSelect>k__BackingField`  
- `private System.Boolean <debugLandValue>k__BackingField`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_DragQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Unity.Entities.EntityQuery m_UpdateQuery`  
- `private Unity.Entities.Entity m_LastRaycastEntity`  
- `private Unity.Mathematics.float3 m_MouseDownPosition`  
- `private Game.Tools.DefaultToolSystem+State m_State`  
- `private Game.Input.IProxyAction m_DefaultToolApply`  
- `private System.Int32 m_LastSelectedIndex`  
- `private Game.Tools.DefaultToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public System.Boolean allowUnderground { get }`  
- `public System.Boolean underground { get; set }`  
- `public System.Boolean ignoreErrors { get; set }`  
- `public System.Boolean allowManipulation { get; set }`  
- `public System.Boolean debugSelect { get; set }`  
- `public System.Boolean debugLandValue { get; set }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

## Constructors

- `public DefaultToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False, System.Boolean toggleSelected = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual ElevationDown() : System.Void`  
- `public virtual ElevationScroll() : System.Void`  
- `public virtual ElevationUp() : System.Void`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private PlaySelectedSound(Unity.Entities.Entity selected, System.Boolean forcePlay = False) : System.Void`  
- `private SelectTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean toggleSelected) : Unity.Jobs.JobHandle`  
- `private SetInfomodeRaycastSettings() : System.Void`  
- `private SetState(Game.Tools.DefaultToolSystem+State state) : System.Void`  
- `public virtual SetUnderground(System.Boolean underground) : System.Void`  
- `private StartDragging(Game.Common.RaycastHit raycastHit) : System.Void`  
- `private StopDragging() : System.Void`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity entity, System.Int32 index, Unity.Mathematics.float3 position, System.Boolean setPosition) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.DefaultToolSystem+State`  
- `Game.Tools.DefaultToolSystem+CreateDefinitionsJob`  
- `Game.Tools.DefaultToolSystem+SelectEntityJob`  
- `Game.Tools.DefaultToolSystem+TypeHandle`  
- `Game.Tools.DefaultToolSystem+<get_toolActions>d__41`  

