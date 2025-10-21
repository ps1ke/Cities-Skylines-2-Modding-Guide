# Game.Simulation.WaterPipeFlowJob+State

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct State
{
    public Game.Simulation.WaterPipeFlowJob+Phase m_Phase;
    public System.Int32 m_LastTotalSteps;
    public System.Int32 m_StepCounter;
    public System.Boolean m_Error;

    public State(System.Int32 lastTotalSteps);

}
```


## Fields

- `public Game.Simulation.WaterPipeFlowJob+Phase m_Phase`  

```csharp
public Game.Simulation.WaterPipeFlowJob+Phase m_Phase;
```

- `public System.Int32 m_LastTotalSteps`  

```csharp
public System.Int32 m_LastTotalSteps;
```

- `public System.Int32 m_StepCounter`  

```csharp
public System.Int32 m_StepCounter;
```

- `public System.Boolean m_Error`  

```csharp
public System.Boolean m_Error;
```


## Constructors

- `public State(System.Int32 lastTotalSteps)`  

```csharp
public State(System.Int32 lastTotalSteps);
```


