# Game.Simulation.ResidentAISystem+ResidentAction

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ResidentAction
{
    public Unity.Entities.Entity m_Citizen;
    public Unity.Entities.Entity m_Target;
    public Unity.Entities.Entity m_Household;
    public Game.Economy.Resource m_Resource;
    public Game.Simulation.ResidentAISystem+ResidentActionType m_Type;
    public System.Int32 m_Amount;
    public System.Single m_Distance;

}
```


## Fields

- `public Unity.Entities.Entity m_Citizen`  

```csharp
public Unity.Entities.Entity m_Citizen;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Unity.Entities.Entity m_Household`  

```csharp
public Unity.Entities.Entity m_Household;
```

- `public Game.Economy.Resource m_Resource`  

```csharp
public Game.Economy.Resource m_Resource;
```

- `public Game.Simulation.ResidentAISystem+ResidentActionType m_Type`  

```csharp
public Game.Simulation.ResidentAISystem+ResidentActionType m_Type;
```

- `public System.Int32 m_Amount`  

```csharp
public System.Int32 m_Amount;
```

- `public System.Single m_Distance`  

```csharp
public System.Single m_Distance;
```


