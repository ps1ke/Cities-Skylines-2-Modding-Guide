# Game.Simulation.TransportBoardingHelpers+BoardingLookupData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct BoardingLookupData
{
    public Unity.Entities.ComponentLookup<Game.Routes.TransportLine> m_TransportLineData;
    public Unity.Entities.ComponentLookup<Game.Routes.Connected> m_ConnectedData;
    public Unity.Entities.ComponentLookup<Game.Routes.TransportStop> m_TransportStopData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_PrefabTransportLineData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportVehicleData> m_PrefabCargoTransportVehicleData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_WatercraftData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.DeliveryTruck> m_DeliveryTruckData;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_LayoutElements;
    public Unity.Entities.BufferLookup<Game.Routes.RouteModifier> m_RouteModifiers;
    public Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransportData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData;
    public Unity.Entities.ComponentLookup<Game.Routes.BoardingVehicle> m_BoardingVehicleData;
    public Unity.Entities.ComponentLookup<Game.Routes.VehicleTiming> m_VehicleTimingData;
    public Unity.Entities.ComponentLookup<Game.Buildings.CargoTransportStation> m_CargoTransportStationData;
    public Unity.Entities.BufferLookup<Game.Companies.StorageTransferRequest> m_StorageTransferRequests;
    public Unity.Entities.BufferLookup<Game.Economy.Resources> m_EconomyResources;
    public Unity.Entities.BufferLookup<Game.Vehicles.LoadingResources> m_LoadingResources;

    public BoardingLookupData(Unity.Entities.SystemBase system);

    public System.Void Update(Unity.Entities.SystemBase system);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Routes.TransportLine> m_TransportLineData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.TransportLine> m_TransportLineData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.Connected> m_ConnectedData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.Connected> m_ConnectedData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.TransportStop> m_TransportStopData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.TransportStop> m_TransportStopData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_PrefabTransportLineData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_PrefabTransportLineData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportVehicleData> m_PrefabCargoTransportVehicleData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportVehicleData> m_PrefabCargoTransportVehicleData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_WatercraftData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_WatercraftData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.DeliveryTruck> m_DeliveryTruckData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.DeliveryTruck> m_DeliveryTruckData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_LayoutElements`  

```csharp
public Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_LayoutElements;
```

- `public Unity.Entities.BufferLookup<Game.Routes.RouteModifier> m_RouteModifiers`  

```csharp
public Unity.Entities.BufferLookup<Game.Routes.RouteModifier> m_RouteModifiers;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransportData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransportData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.BoardingVehicle> m_BoardingVehicleData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.BoardingVehicle> m_BoardingVehicleData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.VehicleTiming> m_VehicleTimingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.VehicleTiming> m_VehicleTimingData;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.CargoTransportStation> m_CargoTransportStationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.CargoTransportStation> m_CargoTransportStationData;
```

- `public Unity.Entities.BufferLookup<Game.Companies.StorageTransferRequest> m_StorageTransferRequests`  

```csharp
public Unity.Entities.BufferLookup<Game.Companies.StorageTransferRequest> m_StorageTransferRequests;
```

- `public Unity.Entities.BufferLookup<Game.Economy.Resources> m_EconomyResources`  

```csharp
public Unity.Entities.BufferLookup<Game.Economy.Resources> m_EconomyResources;
```

- `public Unity.Entities.BufferLookup<Game.Vehicles.LoadingResources> m_LoadingResources`  

```csharp
public Unity.Entities.BufferLookup<Game.Vehicles.LoadingResources> m_LoadingResources;
```


## Constructors

- `public BoardingLookupData(Unity.Entities.SystemBase system)`  

```csharp
public BoardingLookupData(Unity.Entities.SystemBase system);
```


## Methods

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system);
```


