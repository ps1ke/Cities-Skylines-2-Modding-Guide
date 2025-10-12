# Game.City.DevTreeSystem

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_MilestoneReachedQuery`  
- `private Unity.Entities.EntityQuery m_DevTreePointsQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.City.DevTreeSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Int32 points { get; set }`  

## Constructors

- `public DevTreeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static CheckRequirements(Unity.Entities.DynamicBuffer<Game.Prefabs.DevTreeNodeRequirement> requirements, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked) : System.Boolean`  
- `private static CheckService(Unity.Entities.Entity service, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Purchase(Game.Prefabs.DevTreeNodePrefab nodePrefab) : System.Void`  
- `public Purchase(Unity.Entities.Entity node) : System.Void`  

## Nested types

- `Game.City.DevTreeSystem+AppendPointsJob`  
- `Game.City.DevTreeSystem+TypeHandle`  

