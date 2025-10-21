# Game.Pathfind.ModificationJobs+CreateEdgesJob

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`, `Game.Pathfind.ModificationJobs+IPathfindModificationJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CreateEdgesJob : Unity.Jobs.IJob, Game.Pathfind.ModificationJobs+IPathfindModificationJob
{
    public Game.Pathfind.CreateAction m_Action;
    public Game.Pathfind.NativePathfindData m_PathfindData;

    public System.Void Execute();
    public System.Void SetPathfindData(Game.Pathfind.NativePathfindData pathfindData);
}
```


## Fields

- `public Game.Pathfind.CreateAction m_Action`  

```csharp
public Game.Pathfind.CreateAction m_Action;
```

- `public Game.Pathfind.NativePathfindData m_PathfindData`  

```csharp
public Game.Pathfind.NativePathfindData m_PathfindData;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `public SetPathfindData(Game.Pathfind.NativePathfindData pathfindData) : System.Void`  

```csharp
public System.Void SetPathfindData(Game.Pathfind.NativePathfindData pathfindData);
```


