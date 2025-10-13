# Game.Simulation.TrainNavigationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class TrainNavigationHelpers
{
    public static System.Void GetCurvePositions(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Mathematics.float2& pos1, Unity.Mathematics.float2& pos2);
    public static System.Void GetCurvePositions(Game.Vehicles.ParkedTrain& parkedTrain, Unity.Mathematics.float2& pos1, Unity.Mathematics.float2& pos2);
}
```


## Methods

- `public static GetCurvePositions(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Mathematics.float2& pos1, Unity.Mathematics.float2& pos2) : System.Void`  

```csharp
public static System.Void GetCurvePositions(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Mathematics.float2& pos1, Unity.Mathematics.float2& pos2);
```

- `public static GetCurvePositions(Game.Vehicles.ParkedTrain& parkedTrain, Unity.Mathematics.float2& pos1, Unity.Mathematics.float2& pos2) : System.Void`  

```csharp
public static System.Void GetCurvePositions(Game.Vehicles.ParkedTrain& parkedTrain, Unity.Mathematics.float2& pos1, Unity.Mathematics.float2& pos2);
```


## Nested types

- `Game.Simulation.TrainNavigationHelpers+LaneSignal`  
- `Game.Simulation.TrainNavigationHelpers+LaneReservation`  
- `Game.Simulation.TrainNavigationHelpers+LaneEffects`  
- `Game.Simulation.TrainNavigationHelpers+CurrentLaneCache`  
- `Game.Simulation.TrainNavigationHelpers+FindLaneIterator`  

