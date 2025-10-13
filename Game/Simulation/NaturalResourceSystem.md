# Game.Simulation.NaturalResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.NaturalResourceCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NaturalResourceSystem : Game.Simulation.CellMapSystem<Game.Simulation.NaturalResourceCell>, Colossal.Serialization.Entities.IJobSerializable, Game.Serialization.IPostDeserialize
{
    public Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    public Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    public Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    public static readonly System.Int32 kTextureSize;
    public static const System.Int32 MAX_BASE_RESOURCES;
    public static const System.Int32 FERTILITY_REGENERATION_RATE;
    public static const System.Int32 FISH_REGENERATION_RATE;
    public static const System.Int32 UPDATES_PER_DAY;

    public Unity.Mathematics.int2 TextureSize { get; }

    public NaturalResourceSystem();

    internal static System.UInt16 <GetResource>g__FilteringValue|21_0(System.UInt16 p1, System.UInt16 p2, System.UInt16 p3, System.UInt16 p4, Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0& );
    public static Game.Simulation.NaturalResourceAmount GetFertilityAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
    public static Game.Simulation.NaturalResourceAmount GetFishAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
    public static Game.Simulation.NaturalResourceAmount GetOilAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
    public static Game.Simulation.NaturalResourceAmount GetOreAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
    private static Game.Simulation.NaturalResourceAmount GetResource(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map, System.Func<Game.Simulation.NaturalResourceCell, Game.Simulation.NaturalResourceAmount> getter);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Single ResourceAmountToArea(System.Single amount);
    public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `public Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
public Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `public Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
public Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `public Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
public Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static const System.Int32 MAX_BASE_RESOURCES`  

```csharp
public static const System.Int32 MAX_BASE_RESOURCES;
```

- `public static const System.Int32 FERTILITY_REGENERATION_RATE`  

```csharp
public static const System.Int32 FERTILITY_REGENERATION_RATE;
```

- `public static const System.Int32 FISH_REGENERATION_RATE`  

```csharp
public static const System.Int32 FISH_REGENERATION_RATE;
```

- `public static const System.Int32 UPDATES_PER_DAY`  

```csharp
public static const System.Int32 UPDATES_PER_DAY;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public NaturalResourceSystem()`  

```csharp
public NaturalResourceSystem();
```


## Methods

- `internal static <GetResource>g__FilteringValue|21_0(System.UInt16 p1, System.UInt16 p2, System.UInt16 p3, System.UInt16 p4, Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0& ) : System.UInt16`  

```csharp
internal static System.UInt16 <GetResource>g__FilteringValue|21_0(System.UInt16 p1, System.UInt16 p2, System.UInt16 p3, System.UInt16 p4, Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0& );
```

- `public static GetFertilityAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  

```csharp
public static Game.Simulation.NaturalResourceAmount GetFertilityAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
```

- `public static GetFishAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  

```csharp
public static Game.Simulation.NaturalResourceAmount GetFishAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
```

- `public static GetOilAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  

```csharp
public static Game.Simulation.NaturalResourceAmount GetOilAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
```

- `public static GetOreAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  

```csharp
public static Game.Simulation.NaturalResourceAmount GetOreAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
```

- `private static GetResource(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map, System.Func<Game.Simulation.NaturalResourceCell, Game.Simulation.NaturalResourceAmount> getter) : Game.Simulation.NaturalResourceAmount`  

```csharp
private static Game.Simulation.NaturalResourceAmount GetResource(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map, System.Func<Game.Simulation.NaturalResourceCell, Game.Simulation.NaturalResourceAmount> getter);
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

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public ResourceAmountToArea(System.Single amount) : System.Single`  

```csharp
public System.Single ResourceAmountToArea(System.Single amount);
```

- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.NaturalResourceSystem+RegenerateNaturalResourcesJob`  
- `Game.Simulation.NaturalResourceSystem+<>c`  
- `Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0`  

