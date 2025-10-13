# Game.Simulation.TrafficAmbienceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TrafficAmbienceCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Code

```csharp
public class TrafficAmbienceSystem : Game.Simulation.CellMapSystem<Game.Simulation.TrafficAmbienceCell>, Colossal.Serialization.Entities.IJobSerializable
{
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public TrafficAmbienceSystem();

    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.TrafficAmbienceCell GetTrafficAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap);
    public static Game.Simulation.TrafficAmbienceCell GetTrafficAmbience2(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap, System.Single maxPerCell);
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

- `public TrafficAmbienceSystem()`  

```csharp
public TrafficAmbienceSystem();
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public static GetTrafficAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap) : Game.Simulation.TrafficAmbienceCell`  

```csharp
public static Game.Simulation.TrafficAmbienceCell GetTrafficAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap);
```

- `public static GetTrafficAmbience2(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap, System.Single maxPerCell) : Game.Simulation.TrafficAmbienceCell`  

```csharp
public static Game.Simulation.TrafficAmbienceCell GetTrafficAmbience2(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap, System.Single maxPerCell);
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

- `Game.Simulation.TrafficAmbienceSystem+TrafficAmbienceUpdateJob`  

