# Game.Simulation.ISimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ISimulationSystem
{
    public System.UInt32 frameIndex { get; }
    public System.Single frameTime { get; }
    public System.Single selectedSpeed { get; set; }

}
```


## Properties

- `public System.UInt32 frameIndex { get }`  

```csharp
public System.UInt32 frameIndex { get; }
```

- `public System.Single frameTime { get }`  

```csharp
public System.Single frameTime { get; }
```

- `public System.Single selectedSpeed { get; set }`  

```csharp
public System.Single selectedSpeed { get; set; }
```


