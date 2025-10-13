# Game.Simulation.ServiceCoverageSystem+SetupCoverageSearchJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct SetupCoverageSearchJob : Unity.Jobs.IJob
{
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CoverageData> m_PrefabCoverageData;
    public Game.Pathfind.CoverageAction m_Action;
    public Game.Pathfind.PathfindTargetSeeker<Game.Pathfind.PathfindTargetBuffer> m_TargetSeeker;

    public System.Void Execute();
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.CoverageData> m_PrefabCoverageData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.CoverageData> m_PrefabCoverageData;
```

- `public Game.Pathfind.CoverageAction m_Action`  

```csharp
public Game.Pathfind.CoverageAction m_Action;
```

- `public Game.Pathfind.PathfindTargetSeeker<Game.Pathfind.PathfindTargetBuffer> m_TargetSeeker`  

```csharp
public Game.Pathfind.PathfindTargetSeeker<Game.Pathfind.PathfindTargetBuffer> m_TargetSeeker;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


