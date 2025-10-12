# Game.Debug.BuildableAreaDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Debug.BaseDebugSystem+Option m_StrictOption`  
- `private Colossal.Collections.NativeAccumulator<Colossal.Collections.AverageFloat> m_BuildableArea`  
- `private System.Single m_LastBuildableArea`  
- `private Game.Debug.BuildableAreaDebugSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1438325908_0`  

## Properties

- `public System.Single buildableArea { get }`  

## Constructors

- `public BuildableAreaDebugSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Debug.BuildableAreaDebugSystem+BuildableAreaGizmoJob`  
- `Game.Debug.BuildableAreaDebugSystem+TypeHandle`  

