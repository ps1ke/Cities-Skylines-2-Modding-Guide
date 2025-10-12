# Game.Tools.WaterToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.WaterToolSystem+Attribute <attribute>k__BackingField`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Game.Tools.ControlPoint m_RaycastPoint`  
- `private Game.Tools.ControlPoint m_StartPoint`  
- `private Game.Tools.WaterToolSystem+State m_State`  
- `private Game.Tools.WaterToolSystem+TypeHandle __TypeHandle`  
- `public static const System.String kToolID`  

## Properties

- `public System.String toolID { get }`  
- `public Game.Tools.WaterToolSystem+Attribute attribute { get; private set }`  

## Constructors

- `public WaterToolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  
- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private GetAttribute(Game.Tools.ControlPoint controlPoint) : Game.Tools.WaterToolSystem+Attribute`  
- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  
- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  
- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  
- `public virtual InitializeRaycast() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private virtual UpdateActions() : System.Void`  
- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Tools.WaterToolSystem+Attribute`  
- `Game.Tools.WaterToolSystem+State`  
- `Game.Tools.WaterToolSystem+CreateDefinitionsJob`  
- `Game.Tools.WaterToolSystem+TypeHandle`  

