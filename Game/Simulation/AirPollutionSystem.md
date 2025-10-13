# Game.Simulation.AirPollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.AirPollution>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AirPollutionSystem : Game.Simulation.CellMapSystem<Game.Simulation.AirPollution>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    private static readonly System.Int32 kSpread;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public AirPollutionSystem();

    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.AirPollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AirPollution> pollutionMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `private static readonly System.Int32 kSpread`  

```csharp
private static readonly System.Int32 kSpread;
```

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

- `public AirPollutionSystem()`  

```csharp
[Preserve]
	public AirPollutionSystem()
	{
	}
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<AirPollution>.GetCellCenter(index, kTextureSize);
	}
```

- `public static GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AirPollution> pollutionMap) : Game.Simulation.AirPollution`  

```csharp
public static AirPollution GetPollution(float3 position, NativeArray<AirPollution> pollutionMap)
	{
		AirPollution result = default(AirPollution);
		float num = (float)CellMapSystem<AirPollution>.kMapSize / (float)kTextureSize;
		int2 cell = CellMapSystem<AirPollution>.GetCell(position - new float3(num / 2f, 0f, num / 2f), CellMapSystem<AirPollution>.kMapSize, kTextureSize);
		float2 @float = CellMapSystem<AirPollution>.GetCellCoords(position, CellMapSystem<AirPollution>.kMapSize, kTextureSize) - new float2(0.5f, 0.5f);
		cell = math.clamp(cell, 0, kTextureSize - 2);
		short pollution = pollutionMap[cell.x + kTextureSize * cell.y].m_Pollution;
		short pollution2 = pollutionMap[cell.x + 1 + kTextureSize * cell.y].m_Pollution;
		short pollution3 = pollutionMap[cell.x + kTextureSize * (cell.y + 1)].m_Pollution;
		short pollution4 = pollutionMap[cell.x + 1 + kTextureSize * (cell.y + 1)].m_Pollution;
		result.m_Pollution = (short)math.round(math.lerp(math.lerp(pollution, pollution2, @float.x - (float)cell.x), math.lerp(pollution3, pollution4, @float.x - (float)cell.x), @float.y - (float)cell.y));
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
		m_WindSystem = base.World.GetOrCreateSystemManaged<WindSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PollutionParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PollutionParameterData>());
		RequireForUpdate(m_PollutionParameterQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		AirPollutionMoveJob jobData = new AirPollutionMoveJob
		{
			m_PollutionMap = m_Map,
			m_WindMap = m_WindSystem.GetMap(readOnly: true, out dependencies),
			m_PollutionParameters = m_PollutionParameterQuery.GetSingleton<PollutionParameterData>(),
			m_Random = RandomSeed.Next(),
			m_Frame = m_SimulationSystem.frameIndex
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(dependencies, m_WriteDependencies, m_ReadDependencies, base.Dependency));
		m_WindSystem.AddReader(base.Dependency);
		AddWriter(base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.AirPollutionSystem+AirPollutionMoveJob`  

