# Game.Simulation.StorageCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StorageCompanySystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Entities.EntityQuery m_StationGroup;
    private Unity.Entities.EntityQuery m_OCStationGroup;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.StorageCompanySystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kTransferCooldown;
    private static readonly System.Int32 kCostFadeProbability;
    private static readonly System.Single kMaxTransportUnitCost;
    public static readonly System.Int32 kStorageLowStockAmount;
    public static readonly System.Int32 kStationLowStockAmount;
    public static readonly System.Int32 kStorageExportStartAmount;
    public static readonly System.Int32 kStationExportStartAmount;
    private static readonly System.Int32 kStorageMinimalTransferAmount;
    private static readonly System.Int32 kStationMinimalTransferAmount;

    public StorageCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private static System.Boolean ProcessStorage(System.Int32 chunkIndex, Unity.Entities.Entity company, Unity.Entities.Entity building, Game.Economy.Resource resource, Game.Prefabs.StorageCompanyData storageCompanyData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resourceBuffer, Unity.Entities.DynamicBuffer<Game.Companies.StorageTransferRequest> requests, Game.Companies.StorageLimitData limitData, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.DeliveryTruckSelectData truckSelectData, System.UInt32 simulationFrame, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> tradeCosts, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Boolean station, System.Boolean hasConnectedRoute, System.Int32 incomingAmount, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Companies.StorageCompany, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageCompanies, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicles, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.ComponentLookup`1[[Game.Common.Target, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targets, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layoutElements, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Objects.OutsideConnection, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections);
    private static System.Boolean RemoveFromRequests(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.Entity owner, Unity.Entities.Entity target1, Unity.Entities.Entity target2, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Entities.EntityQuery m_StationGroup`  

```csharp
private Unity.Entities.EntityQuery m_StationGroup;
```

- `private Unity.Entities.EntityQuery m_OCStationGroup`  

```csharp
private Unity.Entities.EntityQuery m_OCStationGroup;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.StorageCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StorageCompanySystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kTransferCooldown`  

```csharp
private static readonly System.Int32 kTransferCooldown;
```

- `private static readonly System.Int32 kCostFadeProbability`  

```csharp
private static readonly System.Int32 kCostFadeProbability;
```

- `private static readonly System.Single kMaxTransportUnitCost`  

```csharp
private static readonly System.Single kMaxTransportUnitCost;
```

- `public static readonly System.Int32 kStorageLowStockAmount`  

```csharp
public static readonly System.Int32 kStorageLowStockAmount;
```

- `public static readonly System.Int32 kStationLowStockAmount`  

```csharp
public static readonly System.Int32 kStationLowStockAmount;
```

- `public static readonly System.Int32 kStorageExportStartAmount`  

```csharp
public static readonly System.Int32 kStorageExportStartAmount;
```

- `public static readonly System.Int32 kStationExportStartAmount`  

```csharp
public static readonly System.Int32 kStationExportStartAmount;
```

- `private static readonly System.Int32 kStorageMinimalTransferAmount`  

```csharp
private static readonly System.Int32 kStorageMinimalTransferAmount;
```

- `private static readonly System.Int32 kStationMinimalTransferAmount`  

```csharp
private static readonly System.Int32 kStationMinimalTransferAmount;
```


## Constructors

- `public StorageCompanySystem()`  

```csharp
public StorageCompanySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private static ProcessStorage(System.Int32 chunkIndex, Unity.Entities.Entity company, Unity.Entities.Entity building, Game.Economy.Resource resource, Game.Prefabs.StorageCompanyData storageCompanyData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resourceBuffer, Unity.Entities.DynamicBuffer<Game.Companies.StorageTransferRequest> requests, Game.Companies.StorageLimitData limitData, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.DeliveryTruckSelectData truckSelectData, System.UInt32 simulationFrame, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> tradeCosts, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Boolean station, System.Boolean hasConnectedRoute, System.Int32 incomingAmount, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Companies.StorageCompany, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageCompanies, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicles, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.ComponentLookup`1[[Game.Common.Target, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targets, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layoutElements, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Objects.OutsideConnection, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections) : System.Boolean`  

```csharp
private static System.Boolean ProcessStorage(System.Int32 chunkIndex, Unity.Entities.Entity company, Unity.Entities.Entity building, Game.Economy.Resource resource, Game.Prefabs.StorageCompanyData storageCompanyData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resourceBuffer, Unity.Entities.DynamicBuffer<Game.Companies.StorageTransferRequest> requests, Game.Companies.StorageLimitData limitData, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.DeliveryTruckSelectData truckSelectData, System.UInt32 simulationFrame, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> tradeCosts, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Boolean station, System.Boolean hasConnectedRoute, System.Int32 incomingAmount, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Companies.StorageCompany, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageCompanies, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicles, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.ComponentLookup`1[[Game.Common.Target, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targets, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layoutElements, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Objects.OutsideConnection, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections);
```

- `private static RemoveFromRequests(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.Entity owner, Unity.Entities.Entity target1, Unity.Entities.Entity target2, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests) : System.Boolean`  

```csharp
private static System.Boolean RemoveFromRequests(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.Entity owner, Unity.Entities.Entity target1, Unity.Entities.Entity target2, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests);
```


## Nested types

- `Game.Simulation.StorageCompanySystem+StorageJob`  
- `Game.Simulation.StorageCompanySystem+StationStorageJob`  
- `Game.Simulation.StorageCompanySystem+OCStationStorageJob`  
- `Game.Simulation.StorageCompanySystem+TypeHandle`  

