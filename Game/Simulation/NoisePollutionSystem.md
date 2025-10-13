# Game.Simulation.NoisePollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.NoisePollution>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Code

```csharp
public class NoisePollutionSystem : Game.Simulation.CellMapSystem<Game.Simulation.NoisePollution>, Colossal.Serialization.Entities.IJobSerializable
{
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public NoisePollutionSystem();

    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.NoisePollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> pollutionMap);
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

- `public NoisePollutionSystem()`  

```csharp
[Preserve]
	public NoisePollutionSystem()
	{
	}
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<NoisePollution>.GetCellCenter(index, kTextureSize);
	}
```

- `public static GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> pollutionMap) : Game.Simulation.NoisePollution`  

```csharp
public static NoisePollution GetPollution(float3 position, NativeArray<NoisePollution> pollutionMap)
	{
		NoisePollution result = default(NoisePollution);
		float num = (float)CellMapSystem<NoisePollution>.kMapSize / (float)kTextureSize;
		int2 cell = CellMapSystem<NoisePollution>.GetCell(position - new float3(num / 2f, 0f, num / 2f), CellMapSystem<NoisePollution>.kMapSize, kTextureSize);
		float2 @float = CellMapSystem<NoisePollution>.GetCellCoords(position, CellMapSystem<NoisePollution>.kMapSize, kTextureSize) - new float2(0.5f, 0.5f);
		cell = math.clamp(cell, 0, kTextureSize - 2);
		short pollution = pollutionMap[cell.x + kTextureSize * cell.y].m_Pollution;
		short pollution2 = pollutionMap[cell.x + 1 + kTextureSize * cell.y].m_Pollution;
		short pollution3 = pollutionMap[cell.x + kTextureSize * (cell.y + 1)].m_Pollution;
		short pollution4 = pollutionMap[cell.x + 1 + kTextureSize * (cell.y + 1)].m_Pollution;
		result.m_Pollution = (short)Mathf.RoundToInt(math.lerp(math.lerp(pollution, pollution2, @float.x - (float)cell.x), math.lerp(pollution3, pollution4, @float.x - (float)cell.x), @float.y - (float)cell.y));
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
		JobHandle dependencies;
		NoisePollutionSwapJob jobData = new NoisePollutionSwapJob
		{
			m_PollutionMap = GetMap(readOnly: false, out dependencies)
		};
		dependencies = new NoisePollutionClearJob
		{
			m_PollutionMap = jobData.m_PollutionMap
		}.Schedule(dependsOn: IJobParallelForExtensions.Schedule(jobData, m_Map.Length, 4, dependencies), arrayLength: m_Map.Length, innerloopBatchCount: 64);
		AddWriter(dependencies);
	}
```


## Nested types

- `Game.Simulation.NoisePollutionSystem+NoisePollutionSwapJob`  
- `Game.Simulation.NoisePollutionSystem+NoisePollutionClearJob`  

