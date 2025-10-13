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
[Preserve]
	public ZoneAmbienceSystem()
	{
	}
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<ZoneAmbienceCell>.GetCellCenter(index, kTextureSize);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / kUpdatesPerDay;
	}
```

- `public static GetZoneAmbience(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single maxPerCell) : System.Single`  

```csharp
public static ZoneAmbienceCell GetZoneAmbience(float3 position, NativeArray<ZoneAmbienceCell> zoneAmbienceMap)
	{
		ZoneAmbienceCell result = default(ZoneAmbienceCell);
		int2 cell = CellMapSystem<ZoneAmbienceCell>.GetCell(position, CellMapSystem<ZoneAmbienceCell>.kMapSize, kTextureSize);
		ZoneAmbiences zoneAmbiences = default(ZoneAmbiences);
		float num = 0f;
		for (int i = cell.x - 2; i <= cell.x + 2; i++)
		{
			for (int j = cell.y - 2; j <= cell.y + 2; j++)
			{
				if (i >= 0 && i < kTextureSize && j >= 0 && j < kTextureSize)
				{
					int index = i + kTextureSize * j;
					float num2 = math.max(1f, math.distancesq(GetCellCenter(index), position) / 10f);
					zoneAmbiences += zoneAmbienceMap[index].m_Value / num2;
					num += 1f / num2;
				}
			}
		}
		result.m_Value = zoneAmbiences / num;
		return result;
	}
```

- `public static GetZoneAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap) : Game.Simulation.ZoneAmbienceCell`  

```csharp
public static ZoneAmbienceCell GetZoneAmbience(float3 position, NativeArray<ZoneAmbienceCell> zoneAmbienceMap)
	{
		ZoneAmbienceCell result = default(ZoneAmbienceCell);
		int2 cell = CellMapSystem<ZoneAmbienceCell>.GetCell(position, CellMapSystem<ZoneAmbienceCell>.kMapSize, kTextureSize);
		ZoneAmbiences zoneAmbiences = default(ZoneAmbiences);
		float num = 0f;
		for (int i = cell.x - 2; i <= cell.x + 2; i++)
		{
			for (int j = cell.y - 2; j <= cell.y + 2; j++)
			{
				if (i >= 0 && i < kTextureSize && j >= 0 && j < kTextureSize)
				{
					int index = i + kTextureSize * j;
					float num2 = math.max(1f, math.distancesq(GetCellCenter(index), position) / 10f);
					zoneAmbiences += zoneAmbienceMap[index].m_Value / num2;
					num += 1f / num2;
				}
			}
		}
		result.m_Value = zoneAmbiences / num;
		return result;
	}
```

- `public static GetZoneAmbienceNear(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single nearWeight, System.Single maxPerCell) : System.Single`  

```csharp
public static float GetZoneAmbienceNear(GroupAmbienceType type, float3 position, NativeArray<ZoneAmbienceCell> zoneAmbienceMap, float nearWeight, float maxPerCell)
	{
		int2 cell = CellMapSystem<ZoneAmbienceCell>.GetCell(position, CellMapSystem<ZoneAmbienceCell>.kMapSize, kTextureSize);
		float num = 0f;
		float num2 = 0f;
		for (int i = cell.x - 2; i <= cell.x + 2; i++)
		{
			for (int j = cell.y - 2; j <= cell.y + 2; j++)
			{
				if (i >= 0 && i < kTextureSize && j >= 0 && j < kTextureSize)
				{
					int index = i + kTextureSize * j;
					float num3 = math.max(1f, math.pow(math.distance(GetCellCenter(index), position) / 10f, 1f + nearWeight));
					num += math.min(maxPerCell, zoneAmbienceMap[index].m_Value.GetAmbience(type)) / num3;
					num2 += 1f / num3;
				}
			}
		}
		return num / num2;
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
		ZoneAmbienceUpdateJob jobData = new ZoneAmbienceUpdateJob
		{
			m_ZoneMap = m_Map
		};
		base.Dependency = IJobParallelForExtensions.Schedule(jobData, kTextureSize * kTextureSize, kTextureSize, JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies, base.Dependency));
		AddWriter(base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ZoneAmbienceSystem+ZoneAmbienceUpdateJob`  

