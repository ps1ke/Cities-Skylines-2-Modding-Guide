# Game.Simulation.WindSimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private Unity.Mathematics.float2 <constantWind>k__BackingField`  
- `private System.Single <m_ConstantPressure>k__BackingField`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private System.Boolean m_Odd`  
- `private Unity.Jobs.JobHandle m_Deps`  
- `private Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> m_Cells`  
- `public static readonly System.Int32 kUpdateInterval`  
- `public static readonly Unity.Mathematics.int3 kResolution`  
- `public static readonly System.Single kChangeFactor`  
- `public static readonly System.Single kTerrainSlowdown`  
- `public static readonly System.Single kAirSlowdown`  
- `public static readonly System.Single kVerticalSlowdown`  

## Properties

- `public Unity.Mathematics.float2 constantWind { get; set }`  
- `private System.Single m_ConstantPressure { private get; private set }`  

## Constructors

- `public WindSimulationSystem()`  

## Methods

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  
- `public CreateByteArray<T>(Unity.Collections.NativeArray<T> src) : System.Byte[]`  
- `public DebugLoad() : System.Void`  
- `public DebugSave() : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private GetCell(Unity.Mathematics.int3 position) : Game.Simulation.WindSimulationSystem+WindCell`  
- `public static GetCell(Unity.Mathematics.int3 position, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells) : Game.Simulation.WindSimulationSystem+WindCell`  
- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public GetCells(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell>`  
- `public static GetCenterVelocity(Unity.Mathematics.int3 cell, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells) : Unity.Mathematics.float3`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public SetWind(Unity.Mathematics.float2 direction, System.Single pressure) : System.Void`  

## Nested types

- `Game.Simulation.WindSimulationSystem+WindCell`  
- `Game.Simulation.WindSimulationSystem+UpdateWindVelocityJob`  
- `Game.Simulation.WindSimulationSystem+UpdatePressureJob`  

