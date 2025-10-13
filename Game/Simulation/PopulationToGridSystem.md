# Game.Simulation.PopulationToGridSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.PopulationCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PopulationToGridSystem : Game.Simulation.CellMapSystem<Game.Simulation.PopulationCell>, Colossal.Serialization.Entities.IJobSerializable
{
    private Unity.Entities.EntityQuery m_ResidentialPropertyQuery;
    private Game.Simulation.PopulationToGridSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public PopulationToGridSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.PopulationCell GetPopulation(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.PopulationCell> populationMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ResidentialPropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentialPropertyQuery;
```

- `private Game.Simulation.PopulationToGridSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PopulationToGridSystem+TypeHandle __TypeHandle;
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

- `public PopulationToGridSystem()`  

```csharp
[Preserve]
	public PopulationToGridSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<PopulationCell>.GetCellCenter(index, kTextureSize);
	}
```

- `public static GetPopulation(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.PopulationCell> populationMap) : Game.Simulation.PopulationCell`  

```csharp
public static PopulationCell GetPopulation(float3 position, NativeArray<PopulationCell> populationMap)
	{
		PopulationCell result = default(PopulationCell);
		int2 cell = CellMapSystem<PopulationCell>.GetCell(position, CellMapSystem<PopulationCell>.kMapSize, kTextureSize);
		float2 cellCoords = CellMapSystem<PopulationCell>.GetCellCoords(position, CellMapSystem<PopulationCell>.kMapSize, kTextureSize);
		if (cell.x < 0 || cell.x >= kTextureSize || cell.y < 0 || cell.y >= kTextureSize)
		{
			return result;
		}
		float population = populationMap[cell.x + kTextureSize * cell.y].m_Population;
		float end = ((cell.x < kTextureSize - 1) ? populationMap[cell.x + 1 + kTextureSize * cell.y].m_Population : 0f);
		float start = ((cell.y < kTextureSize - 1) ? populationMap[cell.x + kTextureSize * (cell.y + 1)].m_Population : 0f);
		float end2 = ((cell.x < kTextureSize - 1 && cell.y < kTextureSize - 1) ? populationMap[cell.x + 1 + kTextureSize * (cell.y + 1)].m_Population : 0f);
		result.m_Population = math.lerp(math.lerp(population, end, cellCoords.x - (float)cell.x), math.lerp(start, end2, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y);
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
		m_ResidentialPropertyQuery = GetEntityQuery(ComponentType.ReadOnly<ResidentialProperty>(), ComponentType.ReadOnly<Renter>(), ComponentType.ReadOnly<Transform>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle outJobHandle;
		PopulationToGridJob jobData = new PopulationToGridJob
		{
			m_Entities = m_ResidentialPropertyQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_PopulationMap = m_Map,
			m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef)
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(outJobHandle, m_WriteDependencies, m_ReadDependencies, base.Dependency));
		AddWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.PopulationToGridSystem+PopulationToGridJob`  
- `Game.Simulation.PopulationToGridSystem+TypeHandle`  

