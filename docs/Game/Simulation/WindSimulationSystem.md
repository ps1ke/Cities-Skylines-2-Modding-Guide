# Game.Simulation.WindSimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public class WindSimulationSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Mathematics.float2 <constantWind>k__BackingField;
    private System.Single <m_ConstantPressure>k__BackingField;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private System.Boolean m_Odd;
    private Unity.Jobs.JobHandle m_Deps;
    private Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> m_Cells;
    public static readonly System.Int32 kUpdateInterval;
    public static readonly Unity.Mathematics.int3 kResolution;
    public static readonly System.Single kChangeFactor;
    public static readonly System.Single kTerrainSlowdown;
    public static readonly System.Single kAirSlowdown;
    public static readonly System.Single kVerticalSlowdown;

    public Unity.Mathematics.float2 constantWind { get; set; }
    private System.Single m_ConstantPressure { private get; private set; }

    public WindSimulationSystem();

    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Byte[] CreateByteArray<T>(Unity.Collections.NativeArray<T> src);
    public System.Void DebugLoad();
    public System.Void DebugSave();
    public System.Void Deserialize<TReader>(TReader reader);
    private Game.Simulation.WindSimulationSystem+WindCell GetCell(Unity.Mathematics.int3 position);
    public static Game.Simulation.WindSimulationSystem+WindCell GetCell(Unity.Mathematics.int3 position, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> GetCells(Unity.Jobs.JobHandle& deps);
    public static Unity.Mathematics.float3 GetCenterVelocity(Unity.Mathematics.int3 cell, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Void SetWind(Unity.Mathematics.float2 direction, System.Single pressure);
}
```


## Fields

- `private Unity.Mathematics.float2 <constantWind>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <constantWind>k__BackingField;
```

- `private System.Single <m_ConstantPressure>k__BackingField`  

```csharp
private System.Single <m_ConstantPressure>k__BackingField;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private System.Boolean m_Odd`  

```csharp
private System.Boolean m_Odd;
```

- `private Unity.Jobs.JobHandle m_Deps`  

```csharp
private Unity.Jobs.JobHandle m_Deps;
```

- `private Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> m_Cells`  

```csharp
private Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> m_Cells;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```

- `public static readonly Unity.Mathematics.int3 kResolution`  

```csharp
public static readonly Unity.Mathematics.int3 kResolution;
```

- `public static readonly System.Single kChangeFactor`  

```csharp
public static readonly System.Single kChangeFactor;
```

- `public static readonly System.Single kTerrainSlowdown`  

```csharp
public static readonly System.Single kTerrainSlowdown;
```

- `public static readonly System.Single kAirSlowdown`  

```csharp
public static readonly System.Single kAirSlowdown;
```

- `public static readonly System.Single kVerticalSlowdown`  

```csharp
public static readonly System.Single kVerticalSlowdown;
```


## Properties

- `public Unity.Mathematics.float2 constantWind { get; set }`  

```csharp
public Unity.Mathematics.float2 constantWind { get; set; }
```

- `private System.Single m_ConstantPressure { private get; private set }`  

```csharp
private System.Single m_ConstantPressure { private get; private set; }
```


## Constructors

- `public WindSimulationSystem()`  

```csharp
public WindSimulationSystem();
```


## Methods

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public System.Void AddReader(Unity.Jobs.JobHandle reader);
```

- `public CreateByteArray<T>(Unity.Collections.NativeArray<T> src) : System.Byte[]`  

```csharp
public System.Byte[] CreateByteArray<T>(Unity.Collections.NativeArray<T> src);
```

- `public DebugLoad() : System.Void`  

```csharp
public System.Void DebugLoad();
```

- `public DebugSave() : System.Void`  

```csharp
public System.Void DebugSave();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private GetCell(Unity.Mathematics.int3 position) : Game.Simulation.WindSimulationSystem+WindCell`  

```csharp
private Game.Simulation.WindSimulationSystem+WindCell GetCell(Unity.Mathematics.int3 position);
```

- `public static GetCell(Unity.Mathematics.int3 position, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells) : Game.Simulation.WindSimulationSystem+WindCell`  

```csharp
public static Game.Simulation.WindSimulationSystem+WindCell GetCell(Unity.Mathematics.int3 position, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells);
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public GetCells(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell>`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> GetCells(Unity.Jobs.JobHandle& deps);
```

- `public static GetCenterVelocity(Unity.Mathematics.int3 cell, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCenterVelocity(Unity.Mathematics.int3 cell, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `public SetWind(Unity.Mathematics.float2 direction, System.Single pressure) : System.Void`  

```csharp
public System.Void SetWind(Unity.Mathematics.float2 direction, System.Single pressure);
```


## Nested types

- `Game.Simulation.WindSimulationSystem+WindCell`  
- `Game.Simulation.WindSimulationSystem+UpdateWindVelocityJob`  
- `Game.Simulation.WindSimulationSystem+UpdatePressureJob`  

