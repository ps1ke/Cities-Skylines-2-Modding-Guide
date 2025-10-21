# Game.Simulation.GroundWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.GroundWater>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GroundWaterSystem : Game.Simulation.CellMapSystem<Game.Simulation.GroundWater>, Colossal.Serialization.Entities.IJobSerializable
{
    private Unity.Entities.EntityQuery m_ParameterQuery;
    public static readonly System.Int32 kTextureSize;
    public static const System.Int32 kMaxGroundWater;
    public static const System.Int32 kMinGroundWaterThreshold;

    public GroundWaterSystem();

    internal static System.Void <ConsumeGroundWater>g__ConsumeFraction|9_0(Game.Simulation.GroundWater& gw, System.Single cellAvailable, Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0& );
    private static System.Single Bilinear(System.Int16 v00, System.Int16 v10, System.Int16 v01, System.Int16 v11, System.Single sx, System.Single sy);
    public static System.Void ConsumeGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, System.Int32 amount);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.GroundWater GetGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap);
    private static Game.Simulation.GroundWater GetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    public static System.Boolean IsValidCell(Unity.Mathematics.int2 cell);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
    private static System.Void SetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell, Game.Simulation.GroundWater gw);
    public static System.Boolean TryGetCell(Unity.Mathematics.float3 position, Unity.Mathematics.int2& cell);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static const System.Int32 kMaxGroundWater`  

```csharp
public static const System.Int32 kMaxGroundWater;
```

- `public static const System.Int32 kMinGroundWaterThreshold`  

```csharp
public static const System.Int32 kMinGroundWaterThreshold;
```


## Constructors

- `public GroundWaterSystem()`  

```csharp
public GroundWaterSystem();
```


## Methods

- `internal static <ConsumeGroundWater>g__ConsumeFraction|9_0(Game.Simulation.GroundWater& gw, System.Single cellAvailable, Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0& ) : System.Void`  

```csharp
internal static System.Void <ConsumeGroundWater>g__ConsumeFraction|9_0(Game.Simulation.GroundWater& gw, System.Single cellAvailable, Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0& );
```

- `private static Bilinear(System.Int16 v00, System.Int16 v10, System.Int16 v01, System.Int16 v11, System.Single sx, System.Single sy) : System.Single`  

```csharp
private static System.Single Bilinear(System.Int16 v00, System.Int16 v10, System.Int16 v01, System.Int16 v11, System.Single sx, System.Single sy);
```

- `public static ConsumeGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, System.Int32 amount) : System.Void`  

```csharp
public static System.Void ConsumeGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, System.Int32 amount);
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public static GetGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap) : Game.Simulation.GroundWater`  

```csharp
public static Game.Simulation.GroundWater GetGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap);
```

- `private static GetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell) : Game.Simulation.GroundWater`  

```csharp
private static Game.Simulation.GroundWater GetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
```

- `public static IsValidCell(Unity.Mathematics.int2 cell) : System.Boolean`  

```csharp
public static System.Boolean IsValidCell(Unity.Mathematics.int2 cell);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private static SetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell, Game.Simulation.GroundWater gw) : System.Void`  

```csharp
private static System.Void SetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell, Game.Simulation.GroundWater gw);
```

- `public static TryGetCell(Unity.Mathematics.float3 position, Unity.Mathematics.int2& cell) : System.Boolean`  

```csharp
public static System.Boolean TryGetCell(Unity.Mathematics.float3 position, Unity.Mathematics.int2& cell);
```


## Nested types

- `Game.Simulation.GroundWaterSystem+GroundWaterTickJob`  
- `Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0`  

