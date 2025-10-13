# Game.Prefabs.NetPieceRequirements

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** enum sealed public  

**Base:** `System.Enum`  
**Implements:** `System.IComparable`, `System.ISpanFormattable`, `System.IFormattable`, `System.IConvertible`  

## Code

```csharp
public sealed enum NetPieceRequirements : System.IComparable, System.ISpanFormattable, System.IFormattable, System.IConvertible
{
    public System.Int32 value__;
    public static const Game.Prefabs.NetPieceRequirements Node;
    public static const Game.Prefabs.NetPieceRequirements Intersection;
    public static const Game.Prefabs.NetPieceRequirements DeadEnd;
    public static const Game.Prefabs.NetPieceRequirements Crosswalk;
    public static const Game.Prefabs.NetPieceRequirements BusStop;
    public static const Game.Prefabs.NetPieceRequirements Median;
    public static const Game.Prefabs.NetPieceRequirements TrainStop;
    public static const Game.Prefabs.NetPieceRequirements OppositeTrainStop;
    public static const Game.Prefabs.NetPieceRequirements Inverted;
    public static const Game.Prefabs.NetPieceRequirements TaxiStand;
    public static const Game.Prefabs.NetPieceRequirements LevelCrossing;
    public static const Game.Prefabs.NetPieceRequirements Elevated;
    public static const Game.Prefabs.NetPieceRequirements Tunnel;
    public static const Game.Prefabs.NetPieceRequirements Raised;
    public static const Game.Prefabs.NetPieceRequirements Lowered;
    public static const Game.Prefabs.NetPieceRequirements LowTransition;
    public static const Game.Prefabs.NetPieceRequirements HighTransition;
    public static const Game.Prefabs.NetPieceRequirements WideMedian;
    public static const Game.Prefabs.NetPieceRequirements TramTrack;
    public static const Game.Prefabs.NetPieceRequirements TramStop;
    public static const Game.Prefabs.NetPieceRequirements OppositeTramTrack;
    public static const Game.Prefabs.NetPieceRequirements OppositeTramStop;
    public static const Game.Prefabs.NetPieceRequirements MedianBreak;
    public static const Game.Prefabs.NetPieceRequirements ShipStop;
    public static const Game.Prefabs.NetPieceRequirements Sidewalk;
    public static const Game.Prefabs.NetPieceRequirements Edge;
    public static const Game.Prefabs.NetPieceRequirements SubwayStop;
    public static const Game.Prefabs.NetPieceRequirements OppositeSubwayStop;
    public static const Game.Prefabs.NetPieceRequirements MiddlePlatform;
    public static const Game.Prefabs.NetPieceRequirements Underground;
    public static const Game.Prefabs.NetPieceRequirements Roundabout;
    public static const Game.Prefabs.NetPieceRequirements OppositeSidewalk;
    public static const Game.Prefabs.NetPieceRequirements SoundBarrier;
    public static const Game.Prefabs.NetPieceRequirements Overhead;
    public static const Game.Prefabs.NetPieceRequirements TrafficLights;
    public static const Game.Prefabs.NetPieceRequirements PublicTransportLane;
    public static const Game.Prefabs.NetPieceRequirements OppositePublicTransportLane;
    public static const Game.Prefabs.NetPieceRequirements Spillway;
    public static const Game.Prefabs.NetPieceRequirements MiddleGrass;
    public static const Game.Prefabs.NetPieceRequirements MiddleTrees;
    public static const Game.Prefabs.NetPieceRequirements WideSidewalk;
    public static const Game.Prefabs.NetPieceRequirements SideGrass;
    public static const Game.Prefabs.NetPieceRequirements SideTrees;
    public static const Game.Prefabs.NetPieceRequirements OppositeGrass;
    public static const Game.Prefabs.NetPieceRequirements OppositeTrees;
    public static const Game.Prefabs.NetPieceRequirements Opening;
    public static const Game.Prefabs.NetPieceRequirements Front;
    public static const Game.Prefabs.NetPieceRequirements Back;
    public static const Game.Prefabs.NetPieceRequirements Flipped;
    public static const Game.Prefabs.NetPieceRequirements RemoveTrafficLights;
    public static const Game.Prefabs.NetPieceRequirements AllWayStop;
    public static const Game.Prefabs.NetPieceRequirements Pavement;
    public static const Game.Prefabs.NetPieceRequirements Gravel;
    public static const Game.Prefabs.NetPieceRequirements Tiles;
    public static const Game.Prefabs.NetPieceRequirements ForbidLeftTurn;
    public static const Game.Prefabs.NetPieceRequirements ForbidRightTurn;
    public static const Game.Prefabs.NetPieceRequirements OppositeWideSidewalk;
    public static const Game.Prefabs.NetPieceRequirements OppositeForbidLeftTurn;
    public static const Game.Prefabs.NetPieceRequirements OppositeForbidRightTurn;
    public static const Game.Prefabs.NetPieceRequirements OppositeSoundBarrier;
    public static const Game.Prefabs.NetPieceRequirements SidePlatform;
    public static const Game.Prefabs.NetPieceRequirements AddCrosswalk;
    public static const Game.Prefabs.NetPieceRequirements RemoveCrosswalk;
    public static const Game.Prefabs.NetPieceRequirements Lighting;
    public static const Game.Prefabs.NetPieceRequirements OppositeBusStop;
    public static const Game.Prefabs.NetPieceRequirements OppositeTaxiStand;
    public static const Game.Prefabs.NetPieceRequirements OppositeRaised;
    public static const Game.Prefabs.NetPieceRequirements OppositeLowered;
    public static const Game.Prefabs.NetPieceRequirements OppositeLowTransition;
    public static const Game.Prefabs.NetPieceRequirements OppositeHighTransition;
    public static const Game.Prefabs.NetPieceRequirements OppositeShipStop;
    public static const Game.Prefabs.NetPieceRequirements OppositePlatform;
    public static const Game.Prefabs.NetPieceRequirements OppositeAddCrosswalk;
    public static const Game.Prefabs.NetPieceRequirements OppositeRemoveCrosswalk;
    public static const Game.Prefabs.NetPieceRequirements Inside;
    public static const Game.Prefabs.NetPieceRequirements ForbidStraight;
    public static const Game.Prefabs.NetPieceRequirements OppositeForbidStraight;
    public static const Game.Prefabs.NetPieceRequirements Hidden;
    public static const Game.Prefabs.NetPieceRequirements ParkingSpaces;
    public static const Game.Prefabs.NetPieceRequirements OppositeParkingSpaces;
    public static const Game.Prefabs.NetPieceRequirements FixedNodeSize;
    public static const Game.Prefabs.NetPieceRequirements HalfLength;
    public static const Game.Prefabs.NetPieceRequirements AbruptEnd;
    public static const Game.Prefabs.NetPieceRequirements OppositeAbruptEnd;
    public static const Game.Prefabs.NetPieceRequirements AttachmentTrack;
    public static const Game.Prefabs.NetPieceRequirements EnterGate;
    public static const Game.Prefabs.NetPieceRequirements ExitGate;
    public static const Game.Prefabs.NetPieceRequirements StyleBreak;

}
```


## Fields

- `public System.Int32 value__`  

```csharp
public System.Int32 value__;
```

- `public static const Game.Prefabs.NetPieceRequirements Node`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Node;
```

- `public static const Game.Prefabs.NetPieceRequirements Intersection`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Intersection;
```

- `public static const Game.Prefabs.NetPieceRequirements DeadEnd`  

```csharp
public static const Game.Prefabs.NetPieceRequirements DeadEnd;
```

- `public static const Game.Prefabs.NetPieceRequirements Crosswalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Crosswalk;
```

- `public static const Game.Prefabs.NetPieceRequirements BusStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements BusStop;
```

- `public static const Game.Prefabs.NetPieceRequirements Median`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Median;
```

- `public static const Game.Prefabs.NetPieceRequirements TrainStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements TrainStop;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeTrainStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeTrainStop;
```

- `public static const Game.Prefabs.NetPieceRequirements Inverted`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Inverted;
```

- `public static const Game.Prefabs.NetPieceRequirements TaxiStand`  

```csharp
public static const Game.Prefabs.NetPieceRequirements TaxiStand;
```

- `public static const Game.Prefabs.NetPieceRequirements LevelCrossing`  

```csharp
public static const Game.Prefabs.NetPieceRequirements LevelCrossing;
```

- `public static const Game.Prefabs.NetPieceRequirements Elevated`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Elevated;
```

- `public static const Game.Prefabs.NetPieceRequirements Tunnel`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Tunnel;
```

- `public static const Game.Prefabs.NetPieceRequirements Raised`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Raised;
```

- `public static const Game.Prefabs.NetPieceRequirements Lowered`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Lowered;
```

- `public static const Game.Prefabs.NetPieceRequirements LowTransition`  

```csharp
public static const Game.Prefabs.NetPieceRequirements LowTransition;
```

- `public static const Game.Prefabs.NetPieceRequirements HighTransition`  

```csharp
public static const Game.Prefabs.NetPieceRequirements HighTransition;
```

- `public static const Game.Prefabs.NetPieceRequirements WideMedian`  

```csharp
public static const Game.Prefabs.NetPieceRequirements WideMedian;
```

- `public static const Game.Prefabs.NetPieceRequirements TramTrack`  

```csharp
public static const Game.Prefabs.NetPieceRequirements TramTrack;
```

- `public static const Game.Prefabs.NetPieceRequirements TramStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements TramStop;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeTramTrack`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeTramTrack;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeTramStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeTramStop;
```

- `public static const Game.Prefabs.NetPieceRequirements MedianBreak`  

```csharp
public static const Game.Prefabs.NetPieceRequirements MedianBreak;
```

- `public static const Game.Prefabs.NetPieceRequirements ShipStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements ShipStop;
```

- `public static const Game.Prefabs.NetPieceRequirements Sidewalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Sidewalk;
```

- `public static const Game.Prefabs.NetPieceRequirements Edge`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Edge;
```

- `public static const Game.Prefabs.NetPieceRequirements SubwayStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements SubwayStop;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeSubwayStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeSubwayStop;
```

- `public static const Game.Prefabs.NetPieceRequirements MiddlePlatform`  

```csharp
public static const Game.Prefabs.NetPieceRequirements MiddlePlatform;
```

- `public static const Game.Prefabs.NetPieceRequirements Underground`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Underground;
```

- `public static const Game.Prefabs.NetPieceRequirements Roundabout`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Roundabout;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeSidewalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeSidewalk;
```

- `public static const Game.Prefabs.NetPieceRequirements SoundBarrier`  

```csharp
public static const Game.Prefabs.NetPieceRequirements SoundBarrier;
```

- `public static const Game.Prefabs.NetPieceRequirements Overhead`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Overhead;
```

- `public static const Game.Prefabs.NetPieceRequirements TrafficLights`  

```csharp
public static const Game.Prefabs.NetPieceRequirements TrafficLights;
```

- `public static const Game.Prefabs.NetPieceRequirements PublicTransportLane`  

```csharp
public static const Game.Prefabs.NetPieceRequirements PublicTransportLane;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositePublicTransportLane`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositePublicTransportLane;
```

- `public static const Game.Prefabs.NetPieceRequirements Spillway`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Spillway;
```

- `public static const Game.Prefabs.NetPieceRequirements MiddleGrass`  

```csharp
public static const Game.Prefabs.NetPieceRequirements MiddleGrass;
```

- `public static const Game.Prefabs.NetPieceRequirements MiddleTrees`  

```csharp
public static const Game.Prefabs.NetPieceRequirements MiddleTrees;
```

- `public static const Game.Prefabs.NetPieceRequirements WideSidewalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements WideSidewalk;
```

- `public static const Game.Prefabs.NetPieceRequirements SideGrass`  

```csharp
public static const Game.Prefabs.NetPieceRequirements SideGrass;
```

- `public static const Game.Prefabs.NetPieceRequirements SideTrees`  

```csharp
public static const Game.Prefabs.NetPieceRequirements SideTrees;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeGrass`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeGrass;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeTrees`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeTrees;
```

- `public static const Game.Prefabs.NetPieceRequirements Opening`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Opening;
```

- `public static const Game.Prefabs.NetPieceRequirements Front`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Front;
```

- `public static const Game.Prefabs.NetPieceRequirements Back`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Back;
```

- `public static const Game.Prefabs.NetPieceRequirements Flipped`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Flipped;
```

- `public static const Game.Prefabs.NetPieceRequirements RemoveTrafficLights`  

```csharp
public static const Game.Prefabs.NetPieceRequirements RemoveTrafficLights;
```

- `public static const Game.Prefabs.NetPieceRequirements AllWayStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements AllWayStop;
```

- `public static const Game.Prefabs.NetPieceRequirements Pavement`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Pavement;
```

- `public static const Game.Prefabs.NetPieceRequirements Gravel`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Gravel;
```

- `public static const Game.Prefabs.NetPieceRequirements Tiles`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Tiles;
```

- `public static const Game.Prefabs.NetPieceRequirements ForbidLeftTurn`  

```csharp
public static const Game.Prefabs.NetPieceRequirements ForbidLeftTurn;
```

- `public static const Game.Prefabs.NetPieceRequirements ForbidRightTurn`  

```csharp
public static const Game.Prefabs.NetPieceRequirements ForbidRightTurn;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeWideSidewalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeWideSidewalk;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeForbidLeftTurn`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeForbidLeftTurn;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeForbidRightTurn`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeForbidRightTurn;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeSoundBarrier`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeSoundBarrier;
```

- `public static const Game.Prefabs.NetPieceRequirements SidePlatform`  

```csharp
public static const Game.Prefabs.NetPieceRequirements SidePlatform;
```

- `public static const Game.Prefabs.NetPieceRequirements AddCrosswalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements AddCrosswalk;
```

- `public static const Game.Prefabs.NetPieceRequirements RemoveCrosswalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements RemoveCrosswalk;
```

- `public static const Game.Prefabs.NetPieceRequirements Lighting`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Lighting;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeBusStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeBusStop;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeTaxiStand`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeTaxiStand;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeRaised`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeRaised;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeLowered`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeLowered;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeLowTransition`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeLowTransition;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeHighTransition`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeHighTransition;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeShipStop`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeShipStop;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositePlatform`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositePlatform;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeAddCrosswalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeAddCrosswalk;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeRemoveCrosswalk`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeRemoveCrosswalk;
```

- `public static const Game.Prefabs.NetPieceRequirements Inside`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Inside;
```

- `public static const Game.Prefabs.NetPieceRequirements ForbidStraight`  

```csharp
public static const Game.Prefabs.NetPieceRequirements ForbidStraight;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeForbidStraight`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeForbidStraight;
```

- `public static const Game.Prefabs.NetPieceRequirements Hidden`  

```csharp
public static const Game.Prefabs.NetPieceRequirements Hidden;
```

- `public static const Game.Prefabs.NetPieceRequirements ParkingSpaces`  

```csharp
public static const Game.Prefabs.NetPieceRequirements ParkingSpaces;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeParkingSpaces`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeParkingSpaces;
```

- `public static const Game.Prefabs.NetPieceRequirements FixedNodeSize`  

```csharp
public static const Game.Prefabs.NetPieceRequirements FixedNodeSize;
```

- `public static const Game.Prefabs.NetPieceRequirements HalfLength`  

```csharp
public static const Game.Prefabs.NetPieceRequirements HalfLength;
```

- `public static const Game.Prefabs.NetPieceRequirements AbruptEnd`  

```csharp
public static const Game.Prefabs.NetPieceRequirements AbruptEnd;
```

- `public static const Game.Prefabs.NetPieceRequirements OppositeAbruptEnd`  

```csharp
public static const Game.Prefabs.NetPieceRequirements OppositeAbruptEnd;
```

- `public static const Game.Prefabs.NetPieceRequirements AttachmentTrack`  

```csharp
public static const Game.Prefabs.NetPieceRequirements AttachmentTrack;
```

- `public static const Game.Prefabs.NetPieceRequirements EnterGate`  

```csharp
public static const Game.Prefabs.NetPieceRequirements EnterGate;
```

- `public static const Game.Prefabs.NetPieceRequirements ExitGate`  

```csharp
public static const Game.Prefabs.NetPieceRequirements ExitGate;
```

- `public static const Game.Prefabs.NetPieceRequirements StyleBreak`  

```csharp
public static const Game.Prefabs.NetPieceRequirements StyleBreak;
```


