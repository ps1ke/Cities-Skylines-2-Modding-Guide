# Game.Simulation.ZoneAmbienceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.ZoneAmbienceCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Code

```csharp
public class ZoneAmbienceSystem : Game.Simulation.CellMapSystem<Game.Simulation.ZoneAmbienceCell>, Colossal.Serialization.Entities.IJobSerializable
{
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public ZoneAmbienceSystem();

    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Single GetZoneAmbience(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single maxPerCell);
    public static Game.Simulation.ZoneAmbienceCell GetZoneAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap);
    public static System.Single GetZoneAmbienceNear(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single nearWeight, System.Single maxPerCell);
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

- `public ZoneAmbienceSystem()`  

```csharp
public ZoneAmbienceSystem();
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static GetZoneAmbience(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single maxPerCell) : System.Single`  

```csharp
public static System.Single GetZoneAmbience(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single maxPerCell);
```

- `public static GetZoneAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap) : Game.Simulation.ZoneAmbienceCell`  

```csharp
public static Game.Simulation.ZoneAmbienceCell GetZoneAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap);
```

- `public static GetZoneAmbienceNear(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single nearWeight, System.Single maxPerCell) : System.Single`  

```csharp
public static System.Single GetZoneAmbienceNear(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single nearWeight, System.Single maxPerCell);
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

- `Game.Simulation.ZoneAmbienceSystem+ZoneAmbienceUpdateJob`  

