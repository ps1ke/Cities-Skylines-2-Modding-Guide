# Game.Simulation.ServiceCoverageSystem+PrepareCoverageJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct PrepareCoverageJob : Unity.Jobs.IJob
{
    public Game.Net.CoverageService m_Service;
    public Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> m_BuildingChunks;
    public Unity.Entities.SharedComponentTypeHandle<Game.Net.CoverageServiceType> m_CoverageServiceType;
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.BufferTypeHandle<Game.Pathfind.CoverageElement> m_CoverageElementType;
    public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+BuildingData> m_BuildingData;
    public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+CoverageElement> m_Elements;

    public System.Void Execute();
}
```


## Fields

- `public Game.Net.CoverageService m_Service`  

```csharp
public Game.Net.CoverageService m_Service;
```

- `public Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> m_BuildingChunks`  

```csharp
public Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> m_BuildingChunks;
```

- `public Unity.Entities.SharedComponentTypeHandle<Game.Net.CoverageServiceType> m_CoverageServiceType`  

```csharp
public Unity.Entities.SharedComponentTypeHandle<Game.Net.CoverageServiceType> m_CoverageServiceType;
```

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Pathfind.CoverageElement> m_CoverageElementType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Pathfind.CoverageElement> m_CoverageElementType;
```

- `public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+BuildingData> m_BuildingData`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+BuildingData> m_BuildingData;
```

- `public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+CoverageElement> m_Elements`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+CoverageElement> m_Elements;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


