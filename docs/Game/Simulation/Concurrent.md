# Game.Simulation.TransportBoardingHelpers+BoardingData+Concurrent

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeQueue<Game.Simulation.TransportBoardingHelpers+BoardingItem> m_BoardingQueue`  

## Constructors

- `public Concurrent(Game.Simulation.TransportBoardingHelpers+BoardingData data)`  

## Methods

- `public BeginBoarding(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint, Unity.Entities.Entity currentStation, Unity.Entities.Entity nextStation, System.Boolean refuel) : System.Void`  
- `public BeginTesting(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint) : System.Void`  
- `public EndBoarding(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint, Unity.Entities.Entity currentStation, Unity.Entities.Entity nextStation) : System.Void`  
- `public EndTesting(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint) : System.Void`  

