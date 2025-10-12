# Game.Tools.ApplyPrefabsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_SaveInstanceQuery`  

## Constructors

- `public ApplyPrefabsSystem()`  

## Methods

- `public static AddComponent<T>(Game.Prefabs.PrefabBase asset) : T`  
- `private static CheckCachedValue(Unity.Mathematics.float3& value, Unity.Mathematics.float3 cached) : System.Void`  
- `private static CheckCachedValue(Unity.Mathematics.quaternion& value, Unity.Mathematics.quaternion cached) : System.Void`  
- `private CreateRequirementArray(Game.Prefabs.NetPieceRequirements[] requirementMap, Game.Prefabs.CompositionFlags flags) : Game.Prefabs.NetPieceRequirements[]`  
- `private CreateRequirementMap() : Game.Prefabs.NetPieceRequirements[]`  
- `private GetNodeIndex(Unity.Entities.Entity node, System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> dictionary) : System.Int32`  
- `private GetParentMesh(Unity.Entities.Entity node) : System.Int32`  
- `private HasEdgeStartOrEnd(Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.Entity node, Unity.Entities.Entity instanceEntity) : System.Boolean`  
- `private ListObjectSubAreas(Unity.Entities.Entity instanceEntity, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Collections.Generic.List<Game.Prefabs.ObjectSubAreaInfo>`  
- `private ListObjectSubNets(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubNetInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subNetList, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubLaneInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLaneList, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  
- `private ListObjectSubObjects(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubObjectInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subObjectList, System.Collections.Generic.List`1[[Game.Prefabs.EffectSource+EffectSettings, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subEffectList, System.Collections.Generic.List`1[[Game.Prefabs.ActivityLocation+LocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subActivityList, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static RemoveComponent<T>(Game.Prefabs.PrefabBase asset) : System.Void`  
- `public static RemoveComponent(Game.Prefabs.PrefabBase asset, System.Type componentType) : System.Void`  
- `private UpdateObjectSubAreas(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  
- `private UpdateObjectSubNets(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  
- `private UpdateObjectSubObjects(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

