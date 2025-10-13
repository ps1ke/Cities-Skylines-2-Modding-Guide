# Game.Pathfind.PathfindJobs+PathfindJob

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct PathfindJob : Unity.Jobs.IJob
{
    public Game.Common.RandomSeed m_RandomSeed;
    public Game.Pathfind.NativePathfindData m_PathfindData;
    public Game.Pathfind.PathfindHeuristicData m_PathfindHeuristicData;
    public System.Single m_MaxPassengerTransportSpeed;
    public System.Single m_MaxCargoTransportSpeed;
    public Game.Pathfind.PathfindAction m_Action;

    public System.Void Execute();
    public static System.Void Execute(Game.Pathfind.NativePathfindData pathfindData, Unity.Collections.Allocator allocator, Unity.Mathematics.Random random, Game.Pathfind.PathfindHeuristicData pathfindHeuristicData, System.Single maxPassengerTransportSpeed, System.Single maxCargoTransportSpeed, Game.Pathfind.PathfindActionData& actionData);
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

- `public Game.Pathfind.PathfindAction m_Action`  

```csharp
public Game.Pathfind.PathfindAction m_Action;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `public static Execute(Game.Pathfind.NativePathfindData pathfindData, Unity.Collections.Allocator allocator, Unity.Mathematics.Random random, Game.Pathfind.PathfindHeuristicData pathfindHeuristicData, System.Single maxPassengerTransportSpeed, System.Single maxCargoTransportSpeed, Game.Pathfind.PathfindActionData& actionData) : System.Void`  

```csharp
public static System.Void Execute(Game.Pathfind.NativePathfindData pathfindData, Unity.Collections.Allocator allocator, Unity.Mathematics.Random random, Game.Pathfind.PathfindHeuristicData pathfindHeuristicData, System.Single maxPassengerTransportSpeed, System.Single maxCargoTransportSpeed, Game.Pathfind.PathfindActionData& actionData);
```


