# Game.Simulation.WindSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.Wind>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Code

```csharp
public class WindSystem : Game.Simulation.CellMapSystem<Game.Simulation.Wind>, Colossal.Serialization.Entities.IJobSerializable
{
    public Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
    public Game.Rendering.WindTextureSystem m_WindTextureSystem;
    public Game.Simulation.TerrainSystem m_TerrainSystem;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdateInterval;

    public Unity.Mathematics.int2 TextureSize { get; }

    public WindSystem();

    public virtual Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static Game.Simulation.Wind GetWind(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.Wind> windMap);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `public Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  

```csharp
public Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
```

- `public Game.Rendering.WindTextureSystem m_WindTextureSystem`  

```csharp
public Game.Rendering.WindTextureSystem m_WindTextureSystem;
```

- `public Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
public Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public WindSystem()`  

```csharp
[Preserve]
	public WindSystem()
	{
	}
```


## Methods

- `public virtual Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<Wind>.GetCellCenter(index, kTextureSize);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		if (phase != SystemUpdatePhase.GameSimulation)
		{
			return 1;
		}
		return kUpdateInterval;
	}
```

- `public static GetWind(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.Wind> windMap) : Game.Simulation.Wind`  

```csharp
public static Wind GetWind(float3 position, NativeArray<Wind> windMap)
	{
		int2 cell = CellMapSystem<Wind>.GetCell(position, CellMapSystem<Wind>.kMapSize, kTextureSize);
		cell = math.clamp(cell, 0, kTextureSize - 1);
		float2 cellCoords = CellMapSystem<Wind>.GetCellCoords(position, CellMapSystem<Wind>.kMapSize, kTextureSize);
		int num = math.min(kTextureSize - 1, cell.x + 1);
		int num2 = math.min(kTextureSize - 1, cell.y + 1);
		return new Wind
		{
			m_Wind = math.lerp(math.lerp(windMap[cell.x + kTextureSize * cell.y].m_Wind, windMap[num + kTextureSize * cell.y].m_Wind, cellCoords.x - (float)cell.x), math.lerp(windMap[cell.x + kTextureSize * num2].m_Wind, windMap[num + kTextureSize * num2].m_Wind, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y)
		};
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_WindSimulationSystem = base.World.GetOrCreateSystemManaged<WindSimulationSystem>();
		m_WindTextureSystem = base.World.GetOrCreateSystemManaged<WindTextureSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		CreateTextures(kTextureSize);
		for (int i = 0; i < m_Map.Length; i++)
		{
			m_Map[i] = new Wind
			{
				m_Wind = m_WindSimulationSystem.constantWind
			};
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		TerrainHeightData heightData = m_TerrainSystem.GetHeightData();
		if (heightData.isCreated)
		{
			JobHandle deps;
			WindCopyJob jobData = new WindCopyJob
			{
				m_WindMap = m_Map,
				m_Source = m_WindSimulationSystem.GetCells(out deps),
				m_TerrainHeightData = heightData
			};
			base.Dependency = jobData.Schedule(m_Map.Length, JobHandle.CombineDependencies(deps, JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies, base.Dependency)));
			AddWriter(base.Dependency);
			m_TerrainSystem.AddCPUHeightReader(base.Dependency);
			m_WindSimulationSystem.AddReader(base.Dependency);
			m_WindTextureSystem.RequireUpdate();
		}
	}
```

- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle SetDefaults(Context context)
	{
		m_WindTextureSystem.RequireUpdate();
		for (int i = 0; i < m_Map.Length; i++)
		{
			m_Map[i] = new Wind
			{
				m_Wind = m_WindSimulationSystem.constantWind
			};
		}
		return default(JobHandle);
	}
```


## Nested types

- `Game.Simulation.WindSystem+WindCopyJob`  

