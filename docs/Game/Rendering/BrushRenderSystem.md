# Game.Rendering.BrushRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BrushQuery`  
- `private Unity.Entities.EntityQuery m_SettingsQuery`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private UnityEngine.Mesh m_Mesh`  
- `private UnityEngine.MaterialPropertyBlock m_Properties`  
- `private System.Int32 m_BrushTexture`  
- `private System.Int32 m_BrushOpacity`  
- `private Game.Rendering.BrushRenderSystem+TypeHandle __TypeHandle`  

## Constructors

- `public BrushRenderSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetMesh() : UnityEngine.Mesh`  
- `private GetProperties() : UnityEngine.MaterialPropertyBlock`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PreviewHeight(Game.Tools.Brush brush, Game.Prefabs.BrushPrefab prefab, Game.Prefabs.TerraformingType terraformingType) : System.Void`  
- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

## Nested types

- `Game.Rendering.BrushRenderSystem+TypeHandle`  

