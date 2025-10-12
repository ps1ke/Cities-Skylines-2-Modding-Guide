# Game.Simulation.GroundWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.GroundWater>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ParameterQuery`  
- `public static readonly System.Int32 kTextureSize`  
- `public static const System.Int32 kMaxGroundWater`  
- `public static const System.Int32 kMinGroundWaterThreshold`  

## Constructors

- `public GroundWaterSystem()`  

## Methods

- `internal static <ConsumeGroundWater>g__ConsumeFraction|9_0(Game.Simulation.GroundWater& gw, System.Single cellAvailable, Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0& ) : System.Void`  
- `private static Bilinear(System.Int16 v00, System.Int16 v10, System.Int16 v01, System.Int16 v11, System.Single sx, System.Single sy) : System.Single`  
- `public static ConsumeGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, System.Int32 amount) : System.Void`  
- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public static GetGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap) : Game.Simulation.GroundWater`  
- `private static GetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell) : Game.Simulation.GroundWater`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static IsValidCell(Unity.Mathematics.int2 cell) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  
- `private static SetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell, Game.Simulation.GroundWater gw) : System.Void`  
- `public static TryGetCell(Unity.Mathematics.float3 position, Unity.Mathematics.int2& cell) : System.Boolean`  

## Nested types

- `Game.Simulation.GroundWaterSystem+GroundWaterTickJob`  
- `Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0`  

