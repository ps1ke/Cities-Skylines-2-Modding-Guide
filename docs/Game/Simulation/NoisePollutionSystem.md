# Game.Simulation.NoisePollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.NoisePollution>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Code

```csharp
public class NoisePollutionSystem : Game.Simulation.CellMapSystem<Game.Simulation.NoisePollution>, Colossal.Serialization.Entities.IJobSerializable
{
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public NoisePollutionSystem();

    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.NoisePollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> pollutionMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

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

- `public NoisePollutionSystem()`  

```csharp
public NoisePollutionSystem();
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public static GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> pollutionMap) : Game.Simulation.NoisePollution`  

```csharp
public static Game.Simulation.NoisePollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> pollutionMap);
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

- `Game.Simulation.NoisePollutionSystem+NoisePollutionSwapJob`  
- `Game.Simulation.NoisePollutionSystem+NoisePollutionClearJob`  

