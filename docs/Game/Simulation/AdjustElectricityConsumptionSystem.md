# Game.Simulation.AdjustElectricityConsumptionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AdjustElectricityConsumptionSystem : Game.GameSystemBase
{
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Unity.Entities.EntityQuery m_ConsumerQuery;
    private Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_653552652_0;
    private Unity.Entities.EntityQuery __query_653552652_1;
    private Unity.Entities.EntityQuery __query_653552652_2;
    private static const System.Int32 kFullUpdatesPerDay;

    public AdjustElectricityConsumptionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetFeeConsumptionMultiplier(System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters);
    public static System.Single GetFeeEfficiencyFactor(System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters);
    public System.Single GetTemperatureMultiplier(System.Single temperature);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Unity.Entities.EntityQuery m_ConsumerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerQuery;
```

- `private Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_653552652_0`  

```csharp
private Unity.Entities.EntityQuery __query_653552652_0;
```

- `private Unity.Entities.EntityQuery __query_653552652_1`  

```csharp
private Unity.Entities.EntityQuery __query_653552652_1;
```

- `private Unity.Entities.EntityQuery __query_653552652_2`  

```csharp
private Unity.Entities.EntityQuery __query_653552652_2;
```

- `private static const System.Int32 kFullUpdatesPerDay`  

```csharp
private static const System.Int32 kFullUpdatesPerDay;
```


## Constructors

- `public AdjustElectricityConsumptionSystem()`  

```csharp
public AdjustElectricityConsumptionSystem();
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

- `public GetTemperatureMultiplier(System.Single temperature) : System.Single`  

```csharp
public System.Single GetTemperatureMultiplier(System.Single temperature);
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

- `Game.Simulation.AdjustElectricityConsumptionSystem+AdjustElectricityConsumptionJob`  
- `Game.Simulation.AdjustElectricityConsumptionSystem+UpdateEdgesJob`  
- `Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle`  

