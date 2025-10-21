# Game.Pathfind.AvailabilityJobs+AvailabilityJob

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct AvailabilityJob : Unity.Jobs.IJob
{
    public Game.Pathfind.NativePathfindData m_PathfindData;
    public Game.Pathfind.AvailabilityAction m_Action;

    public System.Void Execute();
    public static System.Void Execute(Game.Pathfind.NativePathfindData pathfindData, Unity.Collections.Allocator allocator, Game.Pathfind.AvailabilityActionData& actionData);
}
```


## Fields

- `public Game.Pathfind.NativePathfindData m_PathfindData`  

```csharp
public Game.Pathfind.NativePathfindData m_PathfindData;
```

- `public Game.Pathfind.AvailabilityAction m_Action`  

```csharp
public Game.Pathfind.AvailabilityAction m_Action;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `public static Execute(Game.Pathfind.NativePathfindData pathfindData, Unity.Collections.Allocator allocator, Game.Pathfind.AvailabilityActionData& actionData) : System.Void`  

```csharp
public static System.Void Execute(Game.Pathfind.NativePathfindData pathfindData, Unity.Collections.Allocator allocator, Game.Pathfind.AvailabilityActionData& actionData);
```


