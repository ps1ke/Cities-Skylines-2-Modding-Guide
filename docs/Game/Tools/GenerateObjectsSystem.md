# Game.Tools.GenerateObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_DeletedQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.ComponentTypeSet m_SubTypes`  
- `private Unity.Entities.ComponentTypeSet m_StoppedUpdateFrameTypes`  
- `private Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> m_ReusedOwnerMap`  
- `private Unity.Jobs.JobHandle m_OwnerMapReadDeps`  
- `private Unity.Jobs.JobHandle m_OwnerMapWriteDeps`  
- `private Game.Tools.GenerateObjectsSystem+TypeHandle __TypeHandle`  

## Constructors

- `public GenerateObjectsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddOwnerMapReader(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public GetReusedOwnerMap(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.GenerateObjectsSystem+CreationData`  
- `Game.Tools.GenerateObjectsSystem+OldObjectKey`  
- `Game.Tools.GenerateObjectsSystem+OldObjectValue`  
- `Game.Tools.GenerateObjectsSystem+FillOldObjectsJob`  
- `Game.Tools.GenerateObjectsSystem+FillCreationListJob`  
- `Game.Tools.GenerateObjectsSystem+CollectCreationDataJob`  
- `Game.Tools.GenerateObjectsSystem+CreateObjectsJob`  
- `Game.Tools.GenerateObjectsSystem+TypeHandle`  

