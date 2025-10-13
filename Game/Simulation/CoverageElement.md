# Game.Simulation.ServiceCoverageSystem+CoverageElement

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Simulation.ServiceCoverageSystem+CoverageElement>`  

## Code

```csharp
public sealed struct CoverageElement : System.IComparable<Game.Simulation.ServiceCoverageSystem+CoverageElement>
{
    public System.Void* m_CoveragePtr;
    public Unity.Mathematics.float2 m_Coverage;
    public System.Single m_AverageCoverage;
    public System.Single m_DensityFactor;
    public System.Single m_LengthFactor;

    public System.Int32 CompareTo(Game.Simulation.ServiceCoverageSystem+CoverageElement other);
}
```


## Fields

- `public System.Void* m_CoveragePtr`  

```csharp
public System.Void* m_CoveragePtr;
```

- `public Unity.Mathematics.float2 m_Coverage`  

```csharp
public Unity.Mathematics.float2 m_Coverage;
```

- `public System.Single m_AverageCoverage`  

```csharp
public System.Single m_AverageCoverage;
```

- `public System.Single m_DensityFactor`  

```csharp
public System.Single m_DensityFactor;
```

- `public System.Single m_LengthFactor`  

```csharp
public System.Single m_LengthFactor;
```


## Methods

- `public CompareTo(Game.Simulation.ServiceCoverageSystem+CoverageElement other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Simulation.ServiceCoverageSystem+CoverageElement other);
```


