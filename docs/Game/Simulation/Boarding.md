# Game.Simulation.ResidentAISystem+Boarding

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.Entity m_Passenger`  
- `public Unity.Entities.Entity m_Leader`  
- `public Unity.Entities.Entity m_Household`  
- `public Unity.Entities.Entity m_Vehicle`  
- `public Unity.Entities.Entity m_LeaderVehicle`  
- `public Unity.Entities.Entity m_Waypoint`  
- `public Game.Creatures.HumanCurrentLane m_CurrentLane`  
- `public Game.Creatures.CreatureVehicleFlags m_Flags`  
- `public Unity.Mathematics.float3 m_Position`  
- `public Unity.Mathematics.quaternion m_Rotation`  
- `public System.Int32 m_TicketPrice`  
- `public Game.Simulation.ResidentAISystem+BoardingType m_Type`  

## Methods

- `public static CancelEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle) : Game.Simulation.ResidentAISystem+Boarding`  
- `public static ExitVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity household, Unity.Entities.Entity vehicle, Game.Creatures.HumanCurrentLane newCurrentLane, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, System.Int32 ticketPrice) : Game.Simulation.ResidentAISystem+Boarding`  
- `public static FinishEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity household, Unity.Entities.Entity vehicle, Unity.Entities.Entity controllerVehicle, Game.Creatures.HumanCurrentLane oldCurrentLane, System.Int32 ticketPrice) : Game.Simulation.ResidentAISystem+Boarding`  
- `public static FinishExitVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle) : Game.Simulation.ResidentAISystem+Boarding`  
- `public static RequireStop(Unity.Entities.Entity passenger, Unity.Entities.Entity vehicle, Unity.Mathematics.float3 position) : Game.Simulation.ResidentAISystem+Boarding`  
- `public static TryEnterVehicle(Unity.Entities.Entity passenger, Unity.Entities.Entity leader, Unity.Entities.Entity vehicle, Unity.Entities.Entity leaderVehicle, Unity.Entities.Entity waypoint, Unity.Mathematics.float3 position, Game.Creatures.CreatureVehicleFlags flags) : Game.Simulation.ResidentAISystem+Boarding`  
- `public static WaitTimeEstimate(Unity.Entities.Entity waypoint, System.Int32 seconds) : Game.Simulation.ResidentAISystem+Boarding`  
- `public static WaitTimeExceeded(Unity.Entities.Entity passenger, Unity.Entities.Entity waypoint) : Game.Simulation.ResidentAISystem+Boarding`  

