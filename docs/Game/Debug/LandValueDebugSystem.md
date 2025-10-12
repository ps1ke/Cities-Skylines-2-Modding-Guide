# Game.Debug.LandValueDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.LandValueSystem m_LandValueSystem`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `private Unity.Entities.EntityQuery m_LandValueEdgeQuery`  
- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  
- `public Game.Debug.BaseDebugSystem+Option m_LandValueCellOption`  
- `private Game.Debug.BaseDebugSystem+Option m_EdgeLandValueOption`  
- `private Game.Debug.LandValueDebugSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Single heightScale`  

## Constructors

- `public LandValueDebugSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static GetColor(UnityEngine.Color a, UnityEngine.Color b, UnityEngine.Color c, System.Single value, System.Single maxValue1, System.Single maxValue2) : UnityEngine.Color`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `public virtual OnDisabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  
- `public virtual OnEnabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Debug.LandValueDebugSystem+LandValueEdgeGizmoJob`  
- `Game.Debug.LandValueDebugSystem+LandValueGizmoJob`  
- `Game.Debug.LandValueDebugSystem+TypeHandle`  

