# Game.Simulation.AvailabilityInfoToGridSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.AvailabilityInfoCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AvailabilityInfoToGridSystem : Game.Simulation.CellMapSystem<Game.Simulation.AvailabilityInfoCell>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public AvailabilityInfoToGridSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Game.Simulation.AvailabilityInfoCell GetAvailabilityInfo(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AvailabilityInfoCell> AvailabilityInfoMap);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle __TypeHandle;
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

- `public AvailabilityInfoToGridSystem()`  

```csharp
[Preserve]
	public AvailabilityInfoToGridSystem()
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

- `public static GetAvailabilityInfo(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AvailabilityInfoCell> AvailabilityInfoMap) : Game.Simulation.AvailabilityInfoCell`  

```csharp
public static AvailabilityInfoCell GetAvailabilityInfo(float3 position, NativeArray<AvailabilityInfoCell> AvailabilityInfoMap)
	{
		AvailabilityInfoCell result = default(AvailabilityInfoCell);
		int2 cell = CellMapSystem<AvailabilityInfoCell>.GetCell(position, CellMapSystem<AvailabilityInfoCell>.kMapSize, kTextureSize);
		float2 cellCoords = CellMapSystem<AvailabilityInfoCell>.GetCellCoords(position, CellMapSystem<AvailabilityInfoCell>.kMapSize, kTextureSize);
		if (cell.x < 0 || cell.x >= kTextureSize || cell.y < 0 || cell.y >= kTextureSize)
		{
			return default(AvailabilityInfoCell);
		}
		float4 availabilityInfo = AvailabilityInfoMap[cell.x + kTextureSize * cell.y].m_AvailabilityInfo;
		float4 end = ((cell.x < kTextureSize - 1) ? AvailabilityInfoMap[cell.x + 1 + kTextureSize * cell.y].m_AvailabilityInfo : ((float4)0));
		float4 start = ((cell.y < kTextureSize - 1) ? AvailabilityInfoMap[cell.x + kTextureSize * (cell.y + 1)].m_AvailabilityInfo : ((float4)0));
		float4 end2 = ((cell.x < kTextureSize - 1 && cell.y < kTextureSize - 1) ? AvailabilityInfoMap[cell.x + 1 + kTextureSize * (cell.y + 1)].m_AvailabilityInfo : ((float4)0));
		result.m_AvailabilityInfo = math.lerp(math.lerp(availabilityInfo, end, cellCoords.x - (float)cell.x), math.lerp(start, end2, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y);
		return result;
	}
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<AvailabilityInfoCell>.GetCellCenter(index, kTextureSize);
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
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
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
		JobHandle dependencies;
		AvailabilityInfoToGridJob jobData = new AvailabilityInfoToGridJob
		{
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_AvailabilityInfoMap = m_Map,
			m_AvailabilityData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CellSize = (float)CellMapSystem<AvailabilityInfoCell>.kMapSize / (float)kTextureSize
		};
		base.Dependency = IJobParallelForExtensions.Schedule(jobData, kTextureSize * kTextureSize, kTextureSize, JobHandle.CombineDependencies(dependencies, JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies, base.Dependency)));
		AddWriter(base.Dependency);
		m_NetSearchSystem.AddNetSearchTreeReader(base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.AvailabilityInfoToGridSystem+NetIterator`  
- `Game.Simulation.AvailabilityInfoToGridSystem+AvailabilityInfoToGridJob`  
- `Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle`  

