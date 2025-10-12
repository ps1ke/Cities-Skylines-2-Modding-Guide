# Game.Rendering.MeshColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <smoothColorsUpdated>k__BackingField`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.RenderPrefabBase m_OverridePrefab`  
- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupIDs`  
- `private Unity.Entities.EntityQuery m_UpdateQuery`  
- `private Unity.Entities.EntityQuery m_AllQuery`  
- `private Unity.Entities.EntityQuery m_PlantQuery`  
- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  
- `private Unity.Entities.Entity m_LastSeason1`  
- `private Unity.Entities.Entity m_LastSeason2`  
- `private Unity.Entities.Entity m_OverrideEntity`  
- `private System.UInt32 m_LastUpdateGroup`  
- `private System.UInt32 m_UpdateGroupCount`  
- `private System.Int32 m_OverrideIndex`  
- `private System.Single m_LastSeasonBlend`  
- `private System.Boolean m_Loaded`  
- `private Game.Rendering.MeshColorSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean smoothColorsUpdated { get; private set }`  

## Constructors

- `public MeshColorSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetColorGroupID(System.String name) : Game.Rendering.ColorGroupID`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private static RandomizeAlphas(Game.Rendering.ColorSet& colorSet, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max) : System.Void`  
- `private static RandomizeColor(UnityEngine.Color& color, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max) : System.Void`  
- `public SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 variationIndex) : System.Void`  

## Nested types

- `Game.Rendering.MeshColorSystem+FindUpdatedMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+ListUpdatedMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+CopyColorData`  
- `Game.Rendering.MeshColorSystem+UpdateStage`  
- `Game.Rendering.MeshColorSystem+SetMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+CopyMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+TypeHandle`  

