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
[Preserve]
	public TrafficAmbienceSystem()
	{
	}
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<TrafficAmbienceCell>.GetCellCenter(index, kTextureSize);
	}
```

- `public static GetTrafficAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap) : Game.Simulation.TrafficAmbienceCell`  

```csharp
public static TrafficAmbienceCell GetTrafficAmbience(float3 position, NativeArray<TrafficAmbienceCell> trafficAmbienceMap)
	{
		TrafficAmbienceCell result = default(TrafficAmbienceCell);
		int2 cell = CellMapSystem<TrafficAmbienceCell>.GetCell(position, CellMapSystem<TrafficAmbienceCell>.kMapSize, kTextureSize);
		if (cell.x < 0 || cell.x >= kTextureSize || cell.y < 0 || cell.y >= kTextureSize)
		{
			return new TrafficAmbienceCell
			{
				m_Accumulator = 0f,
				m_Traffic = 0f
			};
		}
		float2 cellCoords = CellMapSystem<TrafficAmbienceCell>.GetCellCoords(position, CellMapSystem<TrafficAmbienceCell>.kMapSize, kTextureSize);
		float traffic = trafficAmbienceMap[cell.x + kTextureSize * cell.y].m_Traffic;
		float end = ((cell.x < kTextureSize - 1) ? trafficAmbienceMap[cell.x + 1 + kTextureSize * cell.y].m_Traffic : 0f);
		float start = ((cell.y < kTextureSize - 1) ? trafficAmbienceMap[cell.x + kTextureSize * (cell.y + 1)].m_Traffic : 0f);
		float end2 = ((cell.x < kTextureSize - 1 && cell.y < kTextureSize - 1) ? trafficAmbienceMap[cell.x + 1 + kTextureSize * (cell.y + 1)].m_Traffic : 0f);
		result.m_Traffic = math.lerp(math.lerp(traffic, end, cellCoords.x - (float)cell.x), math.lerp(start, end2, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y);
		return result;
	}
```

- `public static GetTrafficAmbience2(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap, System.Single maxPerCell) : Game.Simulation.TrafficAmbienceCell`  

```csharp
public static TrafficAmbienceCell GetTrafficAmbience2(float3 position, NativeArray<TrafficAmbienceCell> trafficAmbienceMap, float maxPerCell)
	{
		TrafficAmbienceCell result = default(TrafficAmbienceCell);
		int2 cell = CellMapSystem<TrafficAmbienceCell>.GetCell(position, CellMapSystem<TrafficAmbienceCell>.kMapSize, kTextureSize);
		float num = 0f;
		float num2 = 0f;
		for (int i = cell.x - 2; i <= cell.x + 2; i++)
		{
			for (int j = cell.y - 2; j <= cell.y + 2; j++)
			{
				if (i >= 0 && i < kTextureSize && j >= 0 && j < kTextureSize)
				{
					int index = i + kTextureSize * j;
					float num3 = math.max(1f, math.distancesq(GetCellCenter(index), position));
					num += math.min(maxPerCell, trafficAmbienceMap[index].m_Traffic) / num3;
					num2 += 1f / num3;
				}
			}
		}
		result.m_Traffic = num / num2;
		return result;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		CreateTextures(kTextureSize);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		TrafficAmbienceUpdateJob jobData = new TrafficAmbienceUpdateJob
		{
			m_TrafficMap = m_Map
		};
		base.Dependency = IJobParallelForExtensions.Schedule(jobData, kTextureSize * kTextureSize, kTextureSize, JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies, base.Dependency));
		AddWriter(base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.TrafficAmbienceSystem+TrafficAmbienceUpdateJob`  

