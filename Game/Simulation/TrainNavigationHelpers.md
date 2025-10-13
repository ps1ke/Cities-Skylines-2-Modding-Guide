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
public static void GetCurvePositions(ref ParkedTrain parkedTrain, out float2 pos1, out float2 pos2)
	{
		pos1 = parkedTrain.m_CurvePosition.x;
		pos2 = parkedTrain.m_CurvePosition.y;
		if (parkedTrain.m_FrontLane == parkedTrain.m_RearLane)
		{
			pos1.x = math.min(pos1.x, pos2.x);
			pos1.y = math.max(pos1.y, pos2.y);
			pos2 = pos1;
		}
	}
```

- `public static GetCurvePositions(Game.Vehicles.ParkedTrain& parkedTrain, Unity.Mathematics.float2& pos1, Unity.Mathematics.float2& pos2) : System.Void`  

```csharp
public static void GetCurvePositions(ref ParkedTrain parkedTrain, out float2 pos1, out float2 pos2)
	{
		pos1 = parkedTrain.m_CurvePosition.x;
		pos2 = parkedTrain.m_CurvePosition.y;
		if (parkedTrain.m_FrontLane == parkedTrain.m_RearLane)
		{
			pos1.x = math.min(pos1.x, pos2.x);
			pos1.y = math.max(pos1.y, pos2.y);
			pos2 = pos1;
		}
	}
```


## Nested types

- `Game.Simulation.TrainNavigationHelpers+LaneSignal`  
- `Game.Simulation.TrainNavigationHelpers+LaneReservation`  
- `Game.Simulation.TrainNavigationHelpers+LaneEffects`  
- `Game.Simulation.TrainNavigationHelpers+CurrentLaneCache`  
- `Game.Simulation.TrainNavigationHelpers+FindLaneIterator`  

