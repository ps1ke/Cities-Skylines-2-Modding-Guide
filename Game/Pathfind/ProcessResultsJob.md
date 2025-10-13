# Game.Pathfind.PathfindJobs+ProcessResultsJob

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ProcessResultsJob : Unity.Jobs.IJobParallelFor
{
    public Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_ResultItems;
    public Unity.Entities.ComponentLookup<Game.Pathfind.PathOwner> m_PathOwner;
    public Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformation;
    public Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
    public Unity.Entities.BufferLookup<Game.Pathfind.PathInformations> m_PathInformations;

    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_ResultItems`  

```csharp
public Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_ResultItems;
```

- `public Unity.Entities.ComponentLookup<Game.Pathfind.PathOwner> m_PathOwner`  

```csharp
public Unity.Entities.ComponentLookup<Game.Pathfind.PathOwner> m_PathOwner;
```

- `public Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformation`  

```csharp
public Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformation;
```

- `public Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  

```csharp
public Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
```

- `public Unity.Entities.BufferLookup<Game.Pathfind.PathInformations> m_PathInformations`  

```csharp
public Unity.Entities.BufferLookup<Game.Pathfind.PathInformations> m_PathInformations;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```


