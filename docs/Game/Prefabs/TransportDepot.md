# Game.Prefabs.TransportDepot

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.TransportType m_TransportType`  
- `public Game.Vehicles.EnergyTypes m_EnergyTypes`  
- `public Game.Vehicles.SizeClass m_SizeClass`  
- `public System.Int32 m_VehicleCapacity`  
- `public System.Single m_ProductionDuration`  
- `public System.Single m_MaintenanceDuration`  
- `public System.Boolean m_DispatchCenter`  

## Constructors

- `public TransportDepot()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

