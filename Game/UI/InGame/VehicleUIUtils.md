# Game.UI.InGame.VehicleUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class VehicleUIUtils
{
    public static System.Int32 GetAvailableVehicles(Unity.Entities.Entity vehicleOwnerEntity, Unity.Entities.EntityManager entityManager);
    public static Unity.Entities.Entity GetDestination(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicleEntity);
    public static Game.UI.InGame.VehicleLocaleKey GetPoliceVehicleLocaleKey(Game.Prefabs.PolicePurpose purposeMask);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PublicTransport publicTransportVehicle, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PersonalCar personalCar, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PostVan postVan, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PoliceCar policeCar, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.MaintenanceVehicle maintenanceVehicle, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Ambulance ambulance, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.GarbageTruck garbageTruck, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.FireEngine fireEngine, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.DeliveryTruck truck, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Hearse hearse, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.CargoTransport cargoTransport, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Taxi taxi, Unity.Entities.EntityManager entityManager);
}
```


## Methods

- `public static GetAvailableVehicles(Unity.Entities.Entity vehicleOwnerEntity, Unity.Entities.EntityManager entityManager) : System.Int32`  

```csharp
public static System.Int32 GetAvailableVehicles(Unity.Entities.Entity vehicleOwnerEntity, Unity.Entities.EntityManager entityManager);
```

- `public static GetDestination(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicleEntity) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetDestination(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicleEntity);
```

- `public static GetPoliceVehicleLocaleKey(Game.Prefabs.PolicePurpose purposeMask) : Game.UI.InGame.VehicleLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleLocaleKey GetPoliceVehicleLocaleKey(Game.Prefabs.PolicePurpose purposeMask);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PublicTransport publicTransportVehicle, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PublicTransport publicTransportVehicle, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PersonalCar personalCar, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PersonalCar personalCar, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PostVan postVan, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PostVan postVan, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PoliceCar policeCar, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PoliceCar policeCar, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.MaintenanceVehicle maintenanceVehicle, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.MaintenanceVehicle maintenanceVehicle, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Ambulance ambulance, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Ambulance ambulance, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.GarbageTruck garbageTruck, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.GarbageTruck garbageTruck, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.FireEngine fireEngine, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.FireEngine fireEngine, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.DeliveryTruck truck, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.DeliveryTruck truck, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Hearse hearse, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Hearse hearse, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.CargoTransport cargoTransport, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.CargoTransport cargoTransport, Unity.Entities.EntityManager entityManager);
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Taxi taxi, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Taxi taxi, Unity.Entities.EntityManager entityManager);
```


## Nested types

- `Game.UI.InGame.VehicleUIUtils+EntityWrapper`  

