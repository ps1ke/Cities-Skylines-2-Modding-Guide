# Game.Buildings.ServiceUpgradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_UpgradeQuery`  
- `private Unity.Entities.EntityQuery m_UpgradePrefabQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  
- `private Game.Buildings.ServiceUpgradeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ServiceUpgradeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private OwnerDeleted(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades) : System.Void`  
- `private UpgradeInstalled(Unity.Entities.EntityCommandBuffer commandBuffer, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef) : System.Void`  
- `private UpgradeRemoved(Unity.Entities.EntityCommandBuffer commandBuffer, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef) : System.Void`  

## Nested types

- `Game.Buildings.ServiceUpgradeSystem+TypeHandle`  

