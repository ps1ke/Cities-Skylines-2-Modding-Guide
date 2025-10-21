# Game.Simulation.AdjustWaterConsumptionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AdjustWaterConsumptionSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Unity.Entities.EntityQuery m_ConsumerQuery;
    private Game.Simulation.AdjustWaterConsumptionSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1300465010_0;
    private Unity.Entities.EntityQuery __query_1300465010_1;
    private static const System.Int32 kFullUpdatesPerDay;

    public AdjustWaterConsumptionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetFeeConsumptionMultiplier(System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters);
    public static System.Single GetFeeEfficiencyFactor(System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Unity.Entities.EntityQuery m_ConsumerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerQuery;
```

- `private Game.Simulation.AdjustWaterConsumptionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AdjustWaterConsumptionSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1300465010_0`  

```csharp
private Unity.Entities.EntityQuery __query_1300465010_0;
```

- `private Unity.Entities.EntityQuery __query_1300465010_1`  

```csharp
private Unity.Entities.EntityQuery __query_1300465010_1;
```

- `private static const System.Int32 kFullUpdatesPerDay`  

```csharp
private static const System.Int32 kFullUpdatesPerDay;
```


## Constructors

- `public AdjustWaterConsumptionSystem()`  

```csharp
public AdjustWaterConsumptionSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetFeeConsumptionMultiplier(System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters) : System.Single`  

```csharp
public static System.Single GetFeeConsumptionMultiplier(System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters);
```

- `public static GetFeeEfficiencyFactor(System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters) : System.Single`  

```csharp
public static System.Single GetFeeEfficiencyFactor(System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.AdjustWaterConsumptionSystem+AdjustWaterConsumptionJob`  
- `Game.Simulation.AdjustWaterConsumptionSystem+UpdateEdgesJob`  
- `Game.Simulation.AdjustWaterConsumptionSystem+TypeHandle`  

