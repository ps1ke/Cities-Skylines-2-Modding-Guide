# Game.Simulation.IServiceFeeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IServiceFeeSystem
{
    public abstract System.Int32 GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee);
    public abstract Unity.Mathematics.int3 GetServiceFees(Game.City.PlayerResource resource);
}
```


## Methods

- `public abstract GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee) : System.Int32`  

```csharp
public abstract System.Int32 GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee);
```

- `public abstract GetServiceFees(Game.City.PlayerResource resource) : Unity.Mathematics.int3`  

```csharp
public abstract Unity.Mathematics.int3 GetServiceFees(Game.City.PlayerResource resource);
```


