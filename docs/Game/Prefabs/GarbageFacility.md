# Game.Prefabs.GarbageFacility

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Int32 m_GarbageCapacity`  
- `public System.Int32 m_VehicleCapacity`  
- `public System.Int32 m_TransportCapacity`  
- `public System.Int32 m_ProcessingSpeed`  
- `public System.Boolean m_IndustrialWasteOnly`  
- `public System.Boolean m_LongTermStorage`  

## Constructors

- `public GarbageFacility()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

