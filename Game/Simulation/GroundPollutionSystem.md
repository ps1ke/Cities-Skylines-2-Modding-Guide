# Game.Simulation.GroundPollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.GroundPollution>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GroundPollutionSystem : Game.Simulation.CellMapSystem<Game.Simulation.GroundPollution>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_PollutionParameterGroup;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public GroundPollutionSystem();

    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.GroundPollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterGroup;
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

- `public GroundPollutionSystem()`  

```csharp
public GroundPollutionSystem();
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public static GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap) : Game.Simulation.GroundPollution`  

```csharp
public static Game.Simulation.GroundPollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap);
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

- `Game.Simulation.GroundPollutionSystem+PollutionFadeJob`  

