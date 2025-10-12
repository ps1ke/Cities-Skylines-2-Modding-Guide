# Game.Pathfind.PathfindQueueSystem+PathfindWorkerJob

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
- `public Unity.Collections.NativeArray<Game.Pathfind.PathfindQueueSystem+WorkerAction> m_Actions`  
- `public Unity.Collections.NativeReference<System.Int32> m_ActionIndex`  
- `public Unity.Collections.AllocatorHelper<Colossal.Collections.UnsafeLinearAllocator> m_Allocator`  

## Methods

- `public Execute() : System.Void`  
- `private Execute(Game.Pathfind.PathfindActionData& actionData, System.Int32 index, Unity.Collections.Allocator allocator) : System.Void`  
- `private Execute(Game.Pathfind.CoverageActionData& actionData, Unity.Collections.Allocator allocator) : System.Void`  
- `private Execute(Game.Pathfind.AvailabilityActionData& actionData, Unity.Collections.Allocator allocator) : System.Void`  

