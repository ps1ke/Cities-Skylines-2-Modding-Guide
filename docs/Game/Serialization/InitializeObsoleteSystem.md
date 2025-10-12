# Game.Serialization.InitializeObsoleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ObsoleteQuery`  
- `private Unity.Entities.EntityQuery m_MeshSettingsQuery`  
- `private System.Collections.Generic.HashSet<Unity.Entities.ComponentType> m_ArchetypeComponents`  
- `private System.Collections.Generic.Dictionary<System.Type, Game.Prefabs.PrefabBase> m_PrefabInstances`  
- `private Game.Serialization.InitializeObsoleteSystem+TypeHandle __TypeHandle`  

## Constructors

- `public InitializeObsoleteSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetArchetype<T>() : Unity.Entities.EntityArchetype`  
- `private GetArchetype<T, TComponentType>() : Unity.Entities.EntityArchetype`  
- `private GetArchetype<T, TComponentType1, TComponentType2>() : Unity.Entities.EntityArchetype`  
- `private GetArchetype<T, TComponentType1, TComponentType2, TComponentType3>() : Unity.Entities.EntityArchetype`  
- `private GetPrefabInstance<T>() : T`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Serialization.InitializeObsoleteSystem+InitializeObsoleteJob`  
- `Game.Serialization.InitializeObsoleteSystem+TypeHandle`  

