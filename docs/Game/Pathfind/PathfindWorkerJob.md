# Game.Pathfind.PathfindQueueSystem+PathfindWorkerJob

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct PathfindWorkerJob : Unity.Jobs.IJob
{
    public Game.Common.RandomSeed m_RandomSeed;
    public Game.Pathfind.NativePathfindData m_PathfindData;
    public Game.Pathfind.PathfindHeuristicData m_PathfindHeuristicData;
    public System.Single m_MaxPassengerTransportSpeed;
    public System.Single m_MaxCargoTransportSpeed;
    public Unity.Collections.NativeArray<Game.Pathfind.PathfindQueueSystem+WorkerAction> m_Actions;
    public Unity.Collections.NativeReference<System.Int32> m_ActionIndex;
    public Unity.Collections.AllocatorHelper<Colossal.Collections.UnsafeLinearAllocator> m_Allocator;

    public System.Void Execute();
    private System.Void Execute(Game.Pathfind.PathfindActionData& actionData, System.Int32 index, Unity.Collections.Allocator allocator);
    private System.Void Execute(Game.Pathfind.CoverageActionData& actionData, Unity.Collections.Allocator allocator);
    private System.Void Execute(Game.Pathfind.AvailabilityActionData& actionData, Unity.Collections.Allocator allocator);
}
```


## Fields

- `public Game.Common.RandomSeed m_RandomSeed`  

```csharp
public Game.Common.RandomSeed m_RandomSeed;
```

- `public Game.Pathfind.NativePathfindData m_PathfindData`  

```csharp
public Game.Pathfind.NativePathfindData m_PathfindData;
```

- `public Game.Pathfind.PathfindHeuristicData m_PathfindHeuristicData`  

```csharp
public Game.Pathfind.PathfindHeuristicData m_PathfindHeuristicData;
```

- `public System.Single m_MaxPassengerTransportSpeed`  

```csharp
public System.Single m_MaxPassengerTransportSpeed;
```

- `public System.Single m_MaxCargoTransportSpeed`  

```csharp
public System.Single m_MaxCargoTransportSpeed;
```

- `public Unity.Collections.NativeArray<Game.Pathfind.PathfindQueueSystem+WorkerAction> m_Actions`  

```csharp
public Unity.Collections.NativeArray<Game.Pathfind.PathfindQueueSystem+WorkerAction> m_Actions;
```

- `public Unity.Collections.NativeReference<System.Int32> m_ActionIndex`  

```csharp
public Unity.Collections.NativeReference<System.Int32> m_ActionIndex;
```

- `public Unity.Collections.AllocatorHelper<Colossal.Collections.UnsafeLinearAllocator> m_Allocator`  

```csharp
public Unity.Collections.AllocatorHelper<Colossal.Collections.UnsafeLinearAllocator> m_Allocator;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private Execute(Game.Pathfind.PathfindActionData& actionData, System.Int32 index, Unity.Collections.Allocator allocator) : System.Void`  

```csharp
private System.Void Execute(Game.Pathfind.PathfindActionData& actionData, System.Int32 index, Unity.Collections.Allocator allocator);
```

- `private Execute(Game.Pathfind.CoverageActionData& actionData, Unity.Collections.Allocator allocator) : System.Void`  

```csharp
private System.Void Execute(Game.Pathfind.CoverageActionData& actionData, Unity.Collections.Allocator allocator);
```

- `private Execute(Game.Pathfind.AvailabilityActionData& actionData, Unity.Collections.Allocator allocator) : System.Void`  

```csharp
private System.Void Execute(Game.Pathfind.AvailabilityActionData& actionData, Unity.Collections.Allocator allocator);
```


