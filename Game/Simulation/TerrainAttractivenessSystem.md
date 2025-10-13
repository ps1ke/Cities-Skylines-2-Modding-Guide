# Game.Simulation.TerrainAttractivenessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TerrainAttractiveness>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TerrainAttractivenessSystem : Game.Simulation.CellMapSystem<Game.Simulation.TerrainAttractiveness>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Unity.Entities.EntityQuery m_AttractivenessParameterGroup;
    private Unity.Collections.NativeArray<Unity.Mathematics.float3> m_AttractFactorData;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public TerrainAttractivenessSystem();

    public static System.Single EvaluateAttractiveness(System.Single terrainHeight, Game.Simulation.TerrainAttractiveness attractiveness, Game.Prefabs.AttractivenessParameterData parameters);
    public static System.Single EvaluateAttractiveness(Unity.Mathematics.float3 position, Game.Simulation.CellMapData<Game.Simulation.TerrainAttractiveness> data, Game.Simulation.TerrainHeightData heightData, Game.Prefabs.AttractivenessParameterData parameters, Unity.Collections.NativeArray<System.Int32> factors);
    public static Game.Simulation.TerrainAttractiveness GetAttractiveness(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TerrainAttractiveness> attractivenessMap);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  

```csharp
private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
```

- `private Unity.Entities.EntityQuery m_AttractivenessParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_AttractivenessParameterGroup;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.float3> m_AttractFactorData`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.float3> m_AttractFactorData;
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

- `public TerrainAttractivenessSystem()`  

```csharp
[Preserve]
	public TerrainAttractivenessSystem()
	{
	}
```


## Methods

- `public static EvaluateAttractiveness(System.Single terrainHeight, Game.Simulation.TerrainAttractiveness attractiveness, Game.Prefabs.AttractivenessParameterData parameters) : System.Single`  

```csharp
public static float EvaluateAttractiveness(float3 position, CellMapData<TerrainAttractiveness> data, TerrainHeightData heightData, AttractivenessParameterData parameters, NativeArray<int> factors)
	{
		float num = TerrainUtils.SampleHeight(ref heightData, position);
		TerrainAttractiveness attractiveness = GetAttractiveness(position, data.m_Buffer);
		float num2 = parameters.m_ForestEffect * attractiveness.m_ForestBonus;
		AttractionSystem.SetFactor(factors, AttractionSystem.AttractivenessFactor.Forest, num2);
		float num3 = parameters.m_ShoreEffect * attractiveness.m_ShoreBonus;
		AttractionSystem.SetFactor(factors, AttractionSystem.AttractivenessFactor.Beach, num3);
		float num4 = math.min(parameters.m_HeightBonus.z, math.max(0f, num - parameters.m_HeightBonus.x) * parameters.m_HeightBonus.y);
		AttractionSystem.SetFactor(factors, AttractionSystem.AttractivenessFactor.Height, num4);
		return num2 + num3 + num4;
	}
```

- `public static EvaluateAttractiveness(Unity.Mathematics.float3 position, Game.Simulation.CellMapData<Game.Simulation.TerrainAttractiveness> data, Game.Simulation.TerrainHeightData heightData, Game.Prefabs.AttractivenessParameterData parameters, Unity.Collections.NativeArray<System.Int32> factors) : System.Single`  

```csharp
public static float EvaluateAttractiveness(float3 position, CellMapData<TerrainAttractiveness> data, TerrainHeightData heightData, AttractivenessParameterData parameters, NativeArray<int> factors)
	{
		float num = TerrainUtils.SampleHeight(ref heightData, position);
		TerrainAttractiveness attractiveness = GetAttractiveness(position, data.m_Buffer);
		float num2 = parameters.m_ForestEffect * attractiveness.m_ForestBonus;
		AttractionSystem.SetFactor(factors, AttractionSystem.AttractivenessFactor.Forest, num2);
		float num3 = parameters.m_ShoreEffect * attractiveness.m_ShoreBonus;
		AttractionSystem.SetFactor(factors, AttractionSystem.AttractivenessFactor.Beach, num3);
		float num4 = math.min(parameters.m_HeightBonus.z, math.max(0f, num - parameters.m_HeightBonus.x) * parameters.m_HeightBonus.y);
		AttractionSystem.SetFactor(factors, AttractionSystem.AttractivenessFactor.Height, num4);
		return num2 + num3 + num4;
	}
```

- `public static GetAttractiveness(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TerrainAttractiveness> attractivenessMap) : Game.Simulation.TerrainAttractiveness`  

```csharp
public static TerrainAttractiveness GetAttractiveness(float3 position, NativeArray<TerrainAttractiveness> attractivenessMap)
	{
		TerrainAttractiveness result = default(TerrainAttractiveness);
		int2 cell = CellMapSystem<TerrainAttractiveness>.GetCell(position, CellMapSystem<TerrainAttractiveness>.kMapSize, kTextureSize);
		float2 cellCoords = CellMapSystem<TerrainAttractiveness>.GetCellCoords(position, CellMapSystem<TerrainAttractiveness>.kMapSize, kTextureSize);
		if (cell.x < 0 || cell.x >= kTextureSize || cell.y < 0 || cell.y >= kTextureSize)
		{
			return result;
		}
		TerrainAttractiveness terrainAttractiveness = attractivenessMap[cell.x + kTextureSize * cell.y];
		TerrainAttractiveness terrainAttractiveness2 = ((cell.x < kTextureSize - 1) ? attractivenessMap[cell.x + 1 + kTextureSize * cell.y] : default(TerrainAttractiveness));
		TerrainAttractiveness terrainAttractiveness3 = ((cell.y < kTextureSize - 1) ? attractivenessMap[cell.x + kTextureSize * (cell.y + 1)] : default(TerrainAttractiveness));
		TerrainAttractiveness terrainAttractiveness4 = ((cell.x < kTextureSize - 1 && cell.y < kTextureSize - 1) ? attractivenessMap[cell.x + 1 + kTextureSize * (cell.y + 1)] : default(TerrainAttractiveness));
		result.m_ForestBonus = (short)Mathf.RoundToInt(math.lerp(math.lerp(terrainAttractiveness.m_ForestBonus, terrainAttractiveness2.m_ForestBonus, cellCoords.x - (float)cell.x), math.lerp(terrainAttractiveness3.m_ForestBonus, terrainAttractiveness4.m_ForestBonus, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y));
		result.m_ShoreBonus = (short)Mathf.RoundToInt(math.lerp(math.lerp(terrainAttractiveness.m_ShoreBonus, terrainAttractiveness2.m_ShoreBonus, cellCoords.x - (float)cell.x), math.lerp(terrainAttractiveness3.m_ShoreBonus, terrainAttractiveness4.m_ShoreBonus, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y));
		return result;
	}
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<TerrainAttractiveness>.GetCellCenter(index, kTextureSize);
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
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_ZoneAmbienceSystem = base.World.GetOrCreateSystemManaged<ZoneAmbienceSystem>();
		m_AttractivenessParameterGroup = GetEntityQuery(ComponentType.ReadOnly<AttractivenessParameterData>());
		m_AttractFactorData = new NativeArray<float3>(m_Map.Length, Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_AttractFactorData.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		TerrainHeightData heightData = m_TerrainSystem.GetHeightData();
		JobHandle deps;
		JobHandle dependencies;
		TerrainAttractivenessPrepareJob jobData = new TerrainAttractivenessPrepareJob
		{
			m_AttractFactorData = m_AttractFactorData,
			m_TerrainData = heightData,
			m_WaterData = m_WaterSystem.GetSurfaceData(out deps),
			m_ZoneAmbienceData = m_ZoneAmbienceSystem.GetData(readOnly: true, out dependencies)
		};
		TerrainAttractivenessJob jobData2 = new TerrainAttractivenessJob
		{
			m_Scale = heightData.scale.x * (float)kTextureSize,
			m_AttractFactorData = m_AttractFactorData,
			m_AttractivenessMap = m_Map,
			m_AttractivenessParameters = m_AttractivenessParameterGroup.GetSingleton<AttractivenessParameterData>()
		};
		JobHandle jobHandle = jobData.ScheduleBatch(m_Map.Length, 4, JobHandle.CombineDependencies(deps, dependencies, base.Dependency));
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_ZoneAmbienceSystem.AddReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		base.Dependency = jobData2.ScheduleBatch(m_Map.Length, 4, JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies, jobHandle));
		AddWriter(base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.TerrainAttractivenessSystem+TerrainAttractivenessPrepareJob`  
- `Game.Simulation.TerrainAttractivenessSystem+TerrainAttractivenessJob`  

