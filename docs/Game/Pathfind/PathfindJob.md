# Game.Pathfind.PathfindJobs+PathfindJob

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Game.Common.RandomSeed m_RandomSeed`  
- `public Game.Pathfind.NativePathfindData m_PathfindData`  
- `public Game.Pathfind.PathfindHeuristicData m_PathfindHeuristicData`  
- `public System.Single m_MaxPassengerTransportSpeed`  
- `public System.Single m_MaxCargoTransportSpeed`  
- `public Game.Pathfind.PathfindAction m_Action`  

## Methods

- `public Execute() : System.Void`  
- `public static Execute(Game.Pathfind.NativePathfindData pathfindData, Unity.Collections.Allocator allocator, Unity.Mathematics.Random random, Game.Pathfind.PathfindHeuristicData pathfindHeuristicData, System.Single maxPassengerTransportSpeed, System.Single maxCargoTransportSpeed, Game.Pathfind.PathfindActionData& actionData) : System.Void`  

