# Game.Simulation.AirPollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.AirPollution>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AirPollutionSystem : Game.Simulation.CellMapSystem<Game.Simulation.AirPollution>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    private static readonly System.Int32 kSpread;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public AirPollutionSystem();

    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.AirPollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AirPollution> pollutionMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `private static readonly System.Int32 kSpread`  

```csharp
private static readonly System.Int32 kSpread;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public AirPollutionSystem()`  

```csharp
public AirPollutionSystem();
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public static GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AirPollution> pollutionMap) : Game.Simulation.AirPollution`  

```csharp
public static Game.Simulation.AirPollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AirPollution> pollutionMap);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.AirPollutionSystem+AirPollutionMoveJob`  

