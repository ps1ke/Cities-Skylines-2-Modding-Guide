# Game.Simulation.SoilWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.SoilWater>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SoilWaterSystem : Game.Simulation.CellMapSystem<Game.Simulation.SoilWater>, Colossal.Serialization.Entities.IJobSerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private UnityEngine.Texture2D m_SoilWaterTexture;
    private Unity.Entities.EntityQuery m_SoilWaterParameterQuery;
    private Unity.Entities.EntityQuery m_FloodQuery;
    private Unity.Entities.EntityQuery m_FloodPrefabQuery;
    private Game.Simulation.SoilWaterSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_336595330_0;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kLoadDistribution;

    public Unity.Mathematics.int2 TextureSize { get; }
    public UnityEngine.Texture soilTexture { get; }

    public SoilWaterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CreateFloodCounter();
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.SoilWater GetSoilWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SoilWater> soilWaterMap);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private UnityEngine.Texture2D m_SoilWaterTexture`  

```csharp
private UnityEngine.Texture2D m_SoilWaterTexture;
```

- `private Unity.Entities.EntityQuery m_SoilWaterParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoilWaterParameterQuery;
```

- `private Unity.Entities.EntityQuery m_FloodQuery`  

```csharp
private Unity.Entities.EntityQuery m_FloodQuery;
```

- `private Unity.Entities.EntityQuery m_FloodPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_FloodPrefabQuery;
```

- `private Game.Simulation.SoilWaterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.SoilWaterSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_336595330_0`  

```csharp
private Unity.Entities.EntityQuery __query_336595330_0;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kLoadDistribution`  

```csharp
public static readonly System.Int32 kLoadDistribution;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```

- `public UnityEngine.Texture soilTexture { get }`  

```csharp
public UnityEngine.Texture soilTexture { get; }
```


## Constructors

- `public SoilWaterSystem()`  

```csharp
[Preserve]
	public SoilWaterSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<FloodCounterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_336595330_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private CreateFloodCounter() : System.Void`  

```csharp
private void CreateFloodCounter()
	{
		base.EntityManager.CreateEntity(base.EntityManager.CreateArchetype(ComponentType.ReadWrite<FloodCounterData>()));
	}
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<SoilWater>.GetCellCenter(index, kTextureSize);
	}
```

- `public static GetSoilWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SoilWater> soilWaterMap) : Game.Simulation.SoilWater`  

```csharp
public static SoilWater GetSoilWater(float3 position, NativeArray<SoilWater> soilWaterMap)
	{
		SoilWater result = default(SoilWater);
		int2 cell = CellMapSystem<SoilWater>.GetCell(position, CellMapSystem<SoilWater>.kMapSize, kTextureSize);
		float2 cellCoords = CellMapSystem<SoilWater>.GetCellCoords(position, CellMapSystem<SoilWater>.kMapSize, kTextureSize);
		if (cell.x < 0 || cell.x >= kTextureSize || cell.y < 0 || cell.y >= kTextureSize)
		{
			return result;
		}
		float start = soilWaterMap[cell.x + kTextureSize * cell.y].m_Amount;
		float end = ((cell.x < kTextureSize - 1) ? soilWaterMap[cell.x + 1 + kTextureSize * cell.y].m_Amount : 0);
		float start2 = ((cell.y < kTextureSize - 1) ? soilWaterMap[cell.x + kTextureSize * (cell.y + 1)].m_Amount : 0);
		float end2 = ((cell.x < kTextureSize - 1 && cell.y < kTextureSize - 1) ? soilWaterMap[cell.x + 1 + kTextureSize * (cell.y + 1)].m_Amount : 0);
		result.m_Amount = (short)Mathf.RoundToInt(math.lerp(math.lerp(start, end, cellCoords.x - (float)cell.x), math.lerp(start2, end2, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y));
		return result;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SoilWaterParameterQuery = GetEntityQuery(ComponentType.ReadOnly<SoilWaterParameterData>());
		m_FloodQuery = GetEntityQuery(ComponentType.ReadOnly<Flood>());
		m_FloodPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<FloodData>());
		CreateFloodCounter();
		CreateTextures(kTextureSize);
		m_SoilWaterTexture = new Texture2D(kTextureSize, kTextureSize, TextureFormat.RFloat, mipChain: false, linear: true)
		{
			name = "SoilWaterTexture",
			hideFlags = HideFlags.HideAndDontSave
		};
		NativeArray<float> rawTextureData = m_SoilWaterTexture.GetRawTextureData<float>();
		for (int i = 0; i < m_Map.Length; i++)
		{
			_ = (float)(i % kTextureSize) / (float)kTextureSize;
			_ = (float)(i / kTextureSize) / (float)kTextureSize;
			SoilWater value = new SoilWater
			{
				m_Amount = 1024,
				m_Max = 8192
			};
			m_Map[i] = value;
			rawTextureData[i] = 0f;
		}
		m_SoilWaterTexture.Apply();
		RequireForUpdate(m_SoilWaterParameterQuery);
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
		TerrainHeightData heightData = m_TerrainSystem.GetHeightData();
		if (heightData.isCreated)
		{
			m_SoilWaterTexture.Apply();
			float value = m_ClimateSystem.precipitation.value;
			int shaderUpdatesPerSoilUpdate = 262144 / (kUpdatesPerDay / kLoadDistribution) / m_WaterSystem.SimulationCycleSteps;
			int loadDistributionIndex = (int)(m_SimulationSystem.frameIndex / (262144 / kUpdatesPerDay) % kLoadDistribution);
			JobHandle deps;
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			SoilWaterTickJob jobData = new SoilWaterTickJob
			{
				m_SoilWaterMap = m_Map,
				m_TerrainHeightData = heightData,
				m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
				m_SoilWaterTextureData = m_SoilWaterTexture.GetRawTextureData<float>(),
				m_SoilWaterParameters = m_SoilWaterParameterQuery.GetSingleton<SoilWaterParameterData>(),
				m_FloodEntities = m_FloodQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_FloodPrefabEntities = m_FloodPrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
				m_Changes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_WaterLevelChange_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Events = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EventData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FloodCounterDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_FloodCounterData_RW_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
				m_FloodCounterEntity = __query_336595330_0.GetSingletonEntity(),
				m_Weather = value,
				m_ShaderUpdatesPerSoilUpdate = shaderUpdatesPerSoilUpdate,
				m_LoadDistributionIndex = loadDistributionIndex
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(m_WriteDependencies, m_ReadDependencies, outJobHandle, outJobHandle2, deps, base.Dependency));
			AddWriter(base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
			m_TerrainSystem.AddCPUHeightReader(base.Dependency);
			m_WaterSystem.AddSurfaceReader(base.Dependency);
			base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadWrite<FloodCounterData>());
		try
		{
			if (entityQuery.CalculateEntityCount() == 0)
			{
				CreateFloodCounter();
			}
		}
		finally
		{
			entityQuery.Dispose();
		}
	}
```


## Nested types

- `Game.Simulation.SoilWaterSystem+SoilWaterTickJob`  
- `Game.Simulation.SoilWaterSystem+TypeHandle`  

