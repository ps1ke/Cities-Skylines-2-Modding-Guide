# Game.Debug.PollutionDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class PollutionDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_GroundOption;
    private Game.Debug.BaseDebugSystem+Option m_AirOption;
    private Game.Debug.BaseDebugSystem+Option m_NoiseOption;

    public PollutionDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_GroundOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GroundOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_AirOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AirOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_NoiseOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_NoiseOption;
```


## Constructors

- `public PollutionDebugSystem()`  

```csharp
public PollutionDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.PollutionDebugSystem+PollutionGizmoJob`  

