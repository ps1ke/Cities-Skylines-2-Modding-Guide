# Game.Prefabs.CargoTransportStation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`, `RequireComponent`  

## Fields

- `public Game.Economy.ResourceInEditor[] m_TradedResources`  
- `public System.Int32 transports`  
- `public Game.Vehicles.EnergyTypes m_CarRefuelTypes`  
- `public Game.Vehicles.EnergyTypes m_TrainRefuelTypes`  
- `public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes`  
- `public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes`  
- `public System.Single m_LoadingFactor`  
- `public System.Single m_WorkMultiplier`  
- `public Unity.Mathematics.int2 m_TransportInterval`  

## Constructors

- `public CargoTransportStation()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

