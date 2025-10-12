# Game.Tools.TerrainToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.TerraformingPrefab <prefab>k__BackingField`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private UnityEngine.AudioSource m_AudioSource`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_BrushQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Unity.Entities.EntityQuery m_VisibleQuery`  
- `private Game.Input.IProxyAction m_EraseMaterial`  
- `private Game.Input.IProxyAction m_EraseResource`  
- `private Game.Input.IProxyAction m_FastSoften`  
- `private Game.Input.IProxyAction m_LevelTerrain`  
- `private Game.Input.IProxyAction m_LowerTerrain`  
- `private Game.Input.IProxyAction m_PaintMaterial`  
- `private Game.Input.IProxyAction m_PaintResource`  
- `private Game.Input.IProxyAction m_RaiseTerrain`  
- `private Game.Input.IProxyAction m_SetLevelTarget`  
- `private Game.Input.IProxyAction m_SetSlopeTarget`  
- `private Game.Input.IProxyAction m_SlopeTerrain`  
- `private Game.Input.IProxyAction m_SoftenTerrain`  
- `private Game.Tools.ControlPoint m_RaycastPoint`  
- `private Game.Tools.ControlPoint m_StartPoint`  
- `private Unity.Mathematics.float3 m_TargetPosition`  
- `private Unity.Mathematics.float3 m_ApplyPosition`  
- `private System.Boolean m_TargetSet`  
- `private Game.Tools.TerrainToolSystem+State m_State`  
- `private Game.Tools.TerrainToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  
- `public static const System.String kTerrainToolKeyGroup`  

## Properties

- `public System.String toolID { get }`  
- `public Game.Prefabs.TerraformingPrefab prefab { get; private set }`  
- `public System.Boolean brushing { get }`  
- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  
- `public System.Single brushHeight { get; set }`  

## Constructors

- `public TerrainToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `private HaveBrushSettingsChanged() : System.Boolean`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetDisableFX() : System.Void`  
- `public SetPrefab(Game.Prefabs.TerraformingPrefab value) : System.Void`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.TerrainToolSystem+State`  
- `Game.Tools.TerrainToolSystem+CreateDefinitionsJob`  
- `Game.Tools.TerrainToolSystem+TypeHandle`  
- `Game.Tools.TerrainToolSystem+<get_toolActions>d__32`  

