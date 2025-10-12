# Game.Rendering.ProceduralUploadSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem`  
- `private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem`  
- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.RenderPrefabBase m_OverridePrefab`  
- `private Colossal.Collections.NativeAccumulator<Game.Rendering.ProceduralUploadSystem+UploadData> m_UploadData`  
- `private Unity.Jobs.JobHandle m_PrepareDeps`  
- `private Unity.Entities.Entity m_OverrideEntity`  
- `private Game.Rendering.LightState m_OverrideLightState`  
- `private System.Int32 m_OverrideSingleLightIndex`  
- `private System.Int32 m_OverrideMultiLightIndex`  
- `private System.Single m_OverrideTime`  
- `private Game.Rendering.ProceduralUploadSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ProceduralUploadSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 singleLightIndex, System.Int32 multiLightIndex) : System.Void`  
- `private UpdateOverride(Game.Rendering.ProceduralUploadSystem+UploadData& emissiveData) : System.Void`  

## Nested types

- `Game.Rendering.ProceduralUploadSystem+Prepare`  
- `Game.Rendering.ProceduralUploadSystem+UploadData`  
- `Game.Rendering.ProceduralUploadSystem+ProceduralPrepareJob`  
- `Game.Rendering.ProceduralUploadSystem+ProceduralUploadJob`  
- `Game.Rendering.ProceduralUploadSystem+TypeHandle`  

