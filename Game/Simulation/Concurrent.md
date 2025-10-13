# Game.Simulation.TransportBoardingHelpers+BoardingData+Concurrent

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Concurrent
{
    private Unity.Collections.NativeQueue<Game.Simulation.TransportBoardingHelpers+BoardingItem> m_BoardingQueue;

    public Concurrent(Game.Simulation.TransportBoardingHelpers+BoardingData data);

    public System.Void BeginBoarding(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint, Unity.Entities.Entity currentStation, Unity.Entities.Entity nextStation, System.Boolean refuel);
    public System.Void BeginTesting(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint);
    public System.Void EndBoarding(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint, Unity.Entities.Entity currentStation, Unity.Entities.Entity nextStation);
    public System.Void EndTesting(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint);
}
```


## Fields

- `private Unity.Collections.NativeQueue<Game.Simulation.TransportBoardingHelpers+BoardingItem> m_BoardingQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.TransportBoardingHelpers+BoardingItem> m_BoardingQueue;
```


## Constructors

- `public Concurrent(Game.Simulation.TransportBoardingHelpers+BoardingData data)`  

```csharp
public Concurrent(Game.Simulation.TransportBoardingHelpers+BoardingData data);
```


## Methods

- `public BeginBoarding(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint, Unity.Entities.Entity currentStation, Unity.Entities.Entity nextStation, System.Boolean refuel) : System.Void`  

```csharp
public System.Void BeginBoarding(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint, Unity.Entities.Entity currentStation, Unity.Entities.Entity nextStation, System.Boolean refuel);
```

- `public BeginTesting(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint) : System.Void`  

```csharp
public System.Void BeginTesting(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint);
```

- `public EndBoarding(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint, Unity.Entities.Entity currentStation, Unity.Entities.Entity nextStation) : System.Void`  

```csharp
public System.Void EndBoarding(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint, Unity.Entities.Entity currentStation, Unity.Entities.Entity nextStation);
```

- `public EndTesting(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint) : System.Void`  

```csharp
public System.Void EndTesting(Unity.Entities.Entity vehicle, Unity.Entities.Entity route, Unity.Entities.Entity stop, Unity.Entities.Entity waypoint);
```


