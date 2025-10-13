# Game.Simulation.IMilestoneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IMilestoneSystem
{
    public System.Int32 currentXP { get; }
    public System.Int32 requiredXP { get; }
    public System.Int32 lastRequiredXP { get; }
    public System.Int32 nextRequiredXP { get; }
    public System.Single progress { get; }
    public System.Int32 nextMilestone { get; }

}
```


## Properties

- `public System.Int32 currentXP { get }`  

```csharp
public System.Int32 currentXP { get; }
```

- `public System.Int32 requiredXP { get }`  

```csharp
public System.Int32 requiredXP { get; }
```

- `public System.Int32 lastRequiredXP { get }`  

```csharp
public System.Int32 lastRequiredXP { get; }
```

- `public System.Int32 nextRequiredXP { get }`  

```csharp
public System.Int32 nextRequiredXP { get; }
```

- `public System.Single progress { get }`  

```csharp
public System.Single progress { get; }
```

- `public System.Int32 nextMilestone { get }`  

```csharp
public System.Int32 nextMilestone { get; }
```


