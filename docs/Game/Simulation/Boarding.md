# Game.Simulation.ResidentAISystem+Boarding

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Boarding
{
    public Unity.Entities.Entity m_Passenger;
    public Unity.Entities.Entity m_Leader;
    public Unity.Entities.Entity m_Household;
    public Unity.Entities.Entity m_Vehicle;
    public Unity.Entities.Entity m_LeaderVehicle;
    public Unity.Entities.Entity m_Waypoint;
    public Game.Creatures.HumanCurrentLane m_CurrentLane;
    public Game.Creatures.CreatureVehicleFlags m_Flags;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;
    public System.Int32 m_TicketPrice;
    public Game.Simulation.ResidentAISystem+BoardingType m_Type;

    public static Game.Simulation.ResidentAISystem+Boarding CancelEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle);
    public static Game.Simulation.ResidentAISystem+Boarding ExitVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity household, Unity.Entities.Entity vehicle, Game.Creatures.HumanCurrentLane newCurrentLane, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, System.Int32 ticketPrice);
    public static Game.Simulation.ResidentAISystem+Boarding FinishEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity household, Unity.Entities.Entity vehicle, Unity.Entities.Entity controllerVehicle, Game.Creatures.HumanCurrentLane oldCurrentLane, System.Int32 ticketPrice);
    public static Game.Simulation.ResidentAISystem+Boarding FinishExitVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle);
    public static Game.Simulation.ResidentAISystem+Boarding RequireStop(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle, Unity.Mathematics.float3 position);
    public static Game.Simulation.ResidentAISystem+Boarding TryEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity leader, Unity.Entities.Entity vehicle, Unity.Entities.Entity leaderVehicle, Unity.Entities.Entity waypoint, Unity.Mathematics.float3 position, Game.Creatures.CreatureVehicleFlags flags);
    public static Game.Simulation.ResidentAISystem+Boarding WaitTimeEstimate(Unity.Entities.Entity waypoint, System.Int32 seconds);
    public static Game.Simulation.ResidentAISystem+Boarding WaitTimeExceeded(Unity.Entities.Entity passenger, Unity.Entities.Entity waypoint);
}
```


## Fields

- `public Unity.Entities.Entity m_Passenger`  

```csharp
public Unity.Entities.Entity m_Passenger;
```

- `public Unity.Entities.Entity m_Leader`  

```csharp
public Unity.Entities.Entity m_Leader;
```

- `public Unity.Entities.Entity m_Household`  

```csharp
public Unity.Entities.Entity m_Household;
```

- `public Unity.Entities.Entity m_Vehicle`  

```csharp
public Unity.Entities.Entity m_Vehicle;
```

- `public Unity.Entities.Entity m_LeaderVehicle`  

```csharp
public Unity.Entities.Entity m_LeaderVehicle;
```

- `public Unity.Entities.Entity m_Waypoint`  

```csharp
public Unity.Entities.Entity m_Waypoint;
```

- `public Game.Creatures.HumanCurrentLane m_CurrentLane`  

```csharp
public Game.Creatures.HumanCurrentLane m_CurrentLane;
```

- `public Game.Creatures.CreatureVehicleFlags m_Flags`  

```csharp
public Game.Creatures.CreatureVehicleFlags m_Flags;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public System.Int32 m_TicketPrice`  

```csharp
public System.Int32 m_TicketPrice;
```

- `public Game.Simulation.ResidentAISystem+BoardingType m_Type`  

```csharp
public Game.Simulation.ResidentAISystem+BoardingType m_Type;
```


## Methods

- `public static CancelEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle) : Game.Simulation.ResidentAISystem+Boarding`  

```csharp
public static Game.Simulation.ResidentAISystem+Boarding CancelEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle);
```

- `public static ExitVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity household, Unity.Entities.Entity vehicle, Game.Creatures.HumanCurrentLane newCurrentLane, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, System.Int32 ticketPrice) : Game.Simulation.ResidentAISystem+Boarding`  

```csharp
public static Game.Simulation.ResidentAISystem+Boarding ExitVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity household, Unity.Entities.Entity vehicle, Game.Creatures.HumanCurrentLane newCurrentLane, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, System.Int32 ticketPrice);
```

- `public static FinishEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity household, Unity.Entities.Entity vehicle, Unity.Entities.Entity controllerVehicle, Game.Creatures.HumanCurrentLane oldCurrentLane, System.Int32 ticketPrice) : Game.Simulation.ResidentAISystem+Boarding`  

```csharp
public static Game.Simulation.ResidentAISystem+Boarding FinishEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity household, Unity.Entities.Entity vehicle, Unity.Entities.Entity controllerVehicle, Game.Creatures.HumanCurrentLane oldCurrentLane, System.Int32 ticketPrice);
```

- `public static FinishExitVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle) : Game.Simulation.ResidentAISystem+Boarding`  

```csharp
public static Game.Simulation.ResidentAISystem+Boarding FinishExitVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle);
```

- `public static RequireStop(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle, Unity.Mathematics.float3 position) : Game.Simulation.ResidentAISystem+Boarding`  

```csharp
public static Game.Simulation.ResidentAISystem+Boarding RequireStop(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle, Unity.Mathematics.float3 position);
```

- `public static TryEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity leader, Unity.Entities.Entity vehicle, Unity.Entities.Entity leaderVehicle, Unity.Entities.Entity waypoint, Unity.Mathematics.float3 position, Game.Creatures.CreatureVehicleFlags flags) : Game.Simulation.ResidentAISystem+Boarding`  

```csharp
public static Game.Simulation.ResidentAISystem+Boarding TryEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity leader, Unity.Entities.Entity vehicle, Unity.Entities.Entity leaderVehicle, Unity.Entities.Entity waypoint, Unity.Mathematics.float3 position, Game.Creatures.CreatureVehicleFlags flags);
```

- `public static WaitTimeEstimate(Unity.Entities.Entity waypoint, System.Int32 seconds) : Game.Simulation.ResidentAISystem+Boarding`  

```csharp
public static Game.Simulation.ResidentAISystem+Boarding WaitTimeEstimate(Unity.Entities.Entity waypoint, System.Int32 seconds);
```

- `public static WaitTimeExceeded(Unity.Entities.Entity passenger, Unity.Entities.Entity waypoint) : Game.Simulation.ResidentAISystem+Boarding`  

```csharp
public static Game.Simulation.ResidentAISystem+Boarding WaitTimeExceeded(Unity.Entities.Entity passenger, Unity.Entities.Entity waypoint);
```


