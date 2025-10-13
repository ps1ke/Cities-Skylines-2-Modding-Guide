# Game.Simulation.ServiceCoverageSystem+ApplyCoverageJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ApplyCoverageJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+BuildingData> m_BuildingData;
    public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+CoverageElement> m_Elements;

    public System.Void Execute();
}
```


## Fields

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


