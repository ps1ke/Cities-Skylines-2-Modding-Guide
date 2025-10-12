# Game.Simulation.TransportBoardingHelpers+BoardingLookupData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Routes.TransportLine> m_TransportLineData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.Connected> m_ConnectedData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.TransportStop> m_TransportStopData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_PrefabTransportLineData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportVehicleData> m_PrefabCargoTransportVehicleData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_WatercraftData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.DeliveryTruck> m_DeliveryTruckData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_LayoutElements`  
- `public Unity.Entities.BufferLookup<Game.Routes.RouteModifier> m_RouteModifiers`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransportData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.BoardingVehicle> m_BoardingVehicleData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.VehicleTiming> m_VehicleTimingData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.CargoTransportStation> m_CargoTransportStationData`  
- `public Unity.Entities.BufferLookup<Game.Companies.StorageTransferRequest> m_StorageTransferRequests`  
- `public Unity.Entities.BufferLookup<Game.Economy.Resources> m_EconomyResources`  
- `public Unity.Entities.BufferLookup<Game.Vehicles.LoadingResources> m_LoadingResources`  

## Constructors

- `public BoardingLookupData(Unity.Entities.SystemBase system)`  

## Methods

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

