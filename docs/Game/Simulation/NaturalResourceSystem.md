# Game.Simulation.NaturalResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.NaturalResourceCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `public Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `public Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  
- `public static readonly System.Int32 kTextureSize`  
- `public static const System.Int32 MAX_BASE_RESOURCES`  
- `public static const System.Int32 FERTILITY_REGENERATION_RATE`  
- `public static const System.Int32 FISH_REGENERATION_RATE`  
- `public static const System.Int32 UPDATES_PER_DAY`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public NaturalResourceSystem()`  

## Methods

- `internal static <GetResource>g__FilteringValue|21_0(System.UInt16 p1, System.UInt16 p2, System.UInt16 p3, System.UInt16 p4, Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0& ) : System.UInt16`  
- `public static GetFertilityAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  
- `public static GetFishAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  
- `public static GetOilAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  
- `public static GetOreAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  
- `private static GetResource(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map, System.Func<Game.Simulation.NaturalResourceCell, Game.Simulation.NaturalResourceAmount> getter) : Game.Simulation.NaturalResourceAmount`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public ResourceAmountToArea(System.Single amount) : System.Single`  
- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.NaturalResourceSystem+RegenerateNaturalResourcesJob`  
- `Game.Simulation.NaturalResourceSystem+<>c`  
- `Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0`  

