# Game.Simulation.GroundPollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.GroundPollution>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GroundPollutionSystem : Game.Simulation.CellMapSystem<Game.Simulation.GroundPollution>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_PollutionParameterGroup;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public GroundPollutionSystem();

    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.GroundPollution GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterGroup;
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

- `public GroundPollutionSystem()`  

```csharp
[Preserve]
	public GroundPollutionSystem()
	{
	}
```


## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<GroundPollution>.GetCellCenter(index, kTextureSize);
	}
```

- `public static GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap) : Game.Simulation.GroundPollution`  

```csharp
public static GroundPollution GetPollution(float3 position, NativeArray<GroundPollution> pollutionMap)
	{
		GroundPollution result = default(GroundPollution);
		int2 cell = CellMapSystem<GroundPollution>.GetCell(position, CellMapSystem<GroundPollution>.kMapSize, kTextureSize);
		float2 cellCoords = CellMapSystem<GroundPollution>.GetCellCoords(position, CellMapSystem<GroundPollution>.kMapSize, kTextureSize);
		if (cell.x < 0 || cell.x >= kTextureSize || cell.y < 0 || cell.y >= kTextureSize)
		{
			return result;
		}
		GroundPollution groundPollution = pollutionMap[cell.x + kTextureSize * cell.y];
		GroundPollution groundPollution2 = ((cell.x < kTextureSize - 1) ? pollutionMap[cell.x + 1 + kTextureSize * cell.y] : default(GroundPollution));
		GroundPollution groundPollution3 = ((cell.y < kTextureSize - 1) ? pollutionMap[cell.x + kTextureSize * (cell.y + 1)] : default(GroundPollution));
		GroundPollution groundPollution4 = ((cell.x < kTextureSize - 1 && cell.y < kTextureSize - 1) ? pollutionMap[cell.x + 1 + kTextureSize * (cell.y + 1)] : default(GroundPollution));
		result.m_Pollution = (short)Mathf.RoundToInt(math.lerp(math.lerp(groundPollution.m_Pollution, groundPollution2.m_Pollution, cellCoords.x - (float)cell.x), math.lerp(groundPollution3.m_Pollution, groundPollution4.m_Pollution, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y));
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		CreateTextures(kTextureSize);
		m_PollutionParameterGroup = GetEntityQuery(ComponentType.ReadOnly<PollutionParameterData>());
		RequireForUpdate(m_PollutionParameterGroup);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		PollutionFadeJob jobData = new PollutionFadeJob
		{
			m_PollutionMap = m_Map,
			m_PollutionParameters = m_PollutionParameterGroup.GetSingleton<PollutionParameterData>(),
			m_Random = RandomSeed.Next(),
			m_Frame = m_SimulationSystem.frameIndex
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies, base.Dependency));
		AddWriter(base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.GroundPollutionSystem+PollutionFadeJob`  

