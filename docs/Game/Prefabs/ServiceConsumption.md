# Game.Prefabs.ServiceConsumption

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Int32 m_Upkeep`  
- `public System.Int32 m_ElectricityConsumption`  
- `public System.Int32 m_WaterConsumption`  
- `public System.Int32 m_GarbageAccumulation`  
- `public System.Single m_TelecomNeed`  

## Constructors

- `public ServiceConsumption()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `private GetConsumptionData() : Game.Prefabs.ConsumptionData`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

