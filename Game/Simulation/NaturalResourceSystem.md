# Game.Simulation.NaturalResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.NaturalResourceCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NaturalResourceSystem : Game.Simulation.CellMapSystem<Game.Simulation.NaturalResourceCell>, Colossal.Serialization.Entities.IJobSerializable, Game.Serialization.IPostDeserialize
{
    public Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    public Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    public Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    public static readonly System.Int32 kTextureSize;
    public static const System.Int32 MAX_BASE_RESOURCES;
    public static const System.Int32 FERTILITY_REGENERATION_RATE;
    public static const System.Int32 FISH_REGENERATION_RATE;
    public static const System.Int32 UPDATES_PER_DAY;

    public Unity.Mathematics.int2 TextureSize { get; }

    public NaturalResourceSystem();

    internal static System.UInt16 <GetResource>g__FilteringValue|21_0(System.UInt16 p1, System.UInt16 p2, System.UInt16 p3, System.UInt16 p4, Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0& );
    public static Game.Simulation.NaturalResourceAmount GetFertilityAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
    public static Game.Simulation.NaturalResourceAmount GetFishAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
    public static Game.Simulation.NaturalResourceAmount GetOilAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
    public static Game.Simulation.NaturalResourceAmount GetOreAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map);
    private static Game.Simulation.NaturalResourceAmount GetResource(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map, System.Func<Game.Simulation.NaturalResourceCell, Game.Simulation.NaturalResourceAmount> getter);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Single ResourceAmountToArea(System.Single amount);
    public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `public Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
public Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `public Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
public Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `public Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
public Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static const System.Int32 MAX_BASE_RESOURCES`  

```csharp
public static const System.Int32 MAX_BASE_RESOURCES;
```

- `public static const System.Int32 FERTILITY_REGENERATION_RATE`  

```csharp
public static const System.Int32 FERTILITY_REGENERATION_RATE;
```

- `public static const System.Int32 FISH_REGENERATION_RATE`  

```csharp
public static const System.Int32 FISH_REGENERATION_RATE;
```

- `public static const System.Int32 UPDATES_PER_DAY`  

```csharp
public static const System.Int32 UPDATES_PER_DAY;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public NaturalResourceSystem()`  

```csharp
[Preserve]
	public NaturalResourceSystem()
	{
	}
```


## Methods

- `internal static <GetResource>g__FilteringValue|21_0(System.UInt16 p1, System.UInt16 p2, System.UInt16 p3, System.UInt16 p4, Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0& ) : System.UInt16`  

```csharp
internal static System.UInt16 <GetResource>g__FilteringValue|21_0(System.UInt16 p1, System.UInt16 p2, System.UInt16 p3, System.UInt16 p4, Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0& );
```

- `public static GetFertilityAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  

```csharp
public static NaturalResourceAmount GetFertilityAmount(float3 position, NativeArray<NaturalResourceCell> map)
	{
		return GetResource(position, map, (NaturalResourceCell c) => c.m_Fertility);
	}
```

- `public static GetFishAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  

```csharp
public static NaturalResourceAmount GetFishAmount(float3 position, NativeArray<NaturalResourceCell> map)
	{
		return GetResource(position, map, (NaturalResourceCell c) => c.m_Fish);
	}
```

- `public static GetOilAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  

```csharp
public static NaturalResourceAmount GetOilAmount(float3 position, NativeArray<NaturalResourceCell> map)
	{
		return GetResource(position, map, (NaturalResourceCell c) => c.m_Oil);
	}
```

- `public static GetOreAmount(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map) : Game.Simulation.NaturalResourceAmount`  

```csharp
public static NaturalResourceAmount GetOreAmount(float3 position, NativeArray<NaturalResourceCell> map)
	{
		return GetResource(position, map, (NaturalResourceCell c) => c.m_Ore);
	}
```

- `private static GetResource(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NaturalResourceCell> map, System.Func<Game.Simulation.NaturalResourceCell, Game.Simulation.NaturalResourceAmount> getter) : Game.Simulation.NaturalResourceAmount`  

```csharp
private static NaturalResourceAmount GetResource(float3 position, NativeArray<NaturalResourceCell> map, Func<NaturalResourceCell, NaturalResourceAmount> getter)
	{
		float num = (float)CellMapSystem<NaturalResourceCell>.kMapSize / (float)kTextureSize;
		int2 cell = CellMapSystem<NaturalResourceCell>.GetCell(position - new float3(num / 2f, 0f, num / 2f), CellMapSystem<NaturalResourceCell>.kMapSize, kTextureSize);
		float2 cellCoords = CellMapSystem<NaturalResourceCell>.GetCellCoords(position, CellMapSystem<NaturalResourceCell>.kMapSize, kTextureSize) - new float2(0.5f, 0.5f);
		cell = math.clamp(cell, 0, kTextureSize - 2);
		NaturalResourceAmount naturalResourceAmount = getter(map[cell.x + kTextureSize * cell.y]);
		NaturalResourceAmount naturalResourceAmount2 = getter(map[cell.x + 1 + kTextureSize * cell.y]);
		NaturalResourceAmount naturalResourceAmount3 = getter(map[cell.x + kTextureSize * (cell.y + 1)]);
		NaturalResourceAmount naturalResourceAmount4 = getter(map[cell.x + 1 + kTextureSize * (cell.y + 1)]);
		return new NaturalResourceAmount
		{
			m_Base = FilteringValue(naturalResourceAmount.m_Base, naturalResourceAmount2.m_Base, naturalResourceAmount3.m_Base, naturalResourceAmount4.m_Base),
			m_Used = FilteringValue(naturalResourceAmount.m_Used, naturalResourceAmount2.m_Used, naturalResourceAmount3.m_Used, naturalResourceAmount4.m_Used)
		};
		ushort FilteringValue(ushort p1, ushort p2, ushort p3, ushort p4)
		{
			return (ushort)math.round(math.lerp(math.lerp((int)p1, (int)p2, cellCoords.x - (float)cell.x), math.lerp((int)p3, (int)p4, cellCoords.x - (float)cell.x), cellCoords.y - (float)cell.y));
		}
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 8192;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_PollutionParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PollutionParameterData>());
		CreateTextures(kTextureSize);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle deps;
		WaterSurfaceData surfaceData = m_WaterSystem.GetSurfaceData(out deps);
		int2 @int = surfaceData.resolution.xz / kTextureSize;
		Assert.AreEqual(GroundPollutionSystem.kTextureSize, kTextureSize, "Ground pollution and Natural resources need to have the same resolution");
		Assert.AreEqual(NoisePollutionSystem.kTextureSize, kTextureSize, "Noise pollution and Natural resources need to have the same resolution");
		Assert.IsTrue(math.all(surfaceData.resolution.xz == @int * kTextureSize), "Water resolution much be dividable with natural resources resolution");
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(new RegenerateNaturalResourcesJob
		{
			m_FertilityRegenerationRate = 25,
			m_FishRegenerationRate = 25,
			m_PollutionRate = m_PollutionParameterQuery.GetSingleton<PollutionParameterData>().m_FertilityGroundMultiplier / 32f,
			m_WaterCellFactor = 300f / (float)(@int.x * @int.y),
			m_RandomSeed = RandomSeed.Next(),
			m_WaterResolutionFactor = @int,
			m_GroundPollutionData = m_GroundPollutionSystem.GetData(readOnly: true, out dependencies),
			m_NoisePollutionData = m_NoisePollutionSystem.GetData(readOnly: true, out dependencies2),
			m_WaterSurfaceData = surfaceData,
			m_CellData = GetData(readOnly: false, out dependencies3)
		}, kTextureSize, 1, JobUtils.CombineDependencies(dependencies, dependencies2, dependencies3, deps));
		AddWriter(jobHandle);
		m_GroundPollutionSystem.AddReader(jobHandle);
		m_NoisePollutionSystem.AddReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (!context.format.Has(FormatTags.FishResource))
		{
			Update();
		}
	}
```

- `public ResourceAmountToArea(System.Single amount) : System.Single`  

```csharp
public float ResourceAmountToArea(float amount)
	{
		float2 @float = (float2)CellMapSystem<NaturalResourceCell>.kMapSize / (float2)TextureSize;
		return amount * @float.x * @float.y / 10000f;
	}
```

- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle SetDefaults(Context context)
	{
		JobHandle result = base.SetDefaults(context);
		if (context.purpose == Purpose.NewGame)
		{
			result.Complete();
			float3 float4 = default(float3);
			for (int i = 0; i < m_Map.Length; i++)
			{
				float num = (float)(i % kTextureSize) / (float)kTextureSize;
				float num2 = (float)(i / kTextureSize) / (float)kTextureSize;
				float3 @float = new float3(6.1f, 13.9f, 10.7f);
				float3 float2 = num * @float;
				float3 float3 = num2 * @float;
				float4.x = Mathf.PerlinNoise(float2.x, float3.x);
				float4.y = Mathf.PerlinNoise(float2.y, float3.y);
				float4.z = Mathf.PerlinNoise(float2.z, float3.z);
				float4 = (float4 - new float3(0.4f, 0.7f, 0.7f)) * new float3(5f, 10f, 10f);
				float4 = 10000f * math.saturate(float4);
				NaturalResourceCell value = new NaturalResourceCell
				{
					m_Fertility = 
					{
						m_Base = (ushort)float4.x
					},
					m_Ore = 
					{
						m_Base = (ushort)float4.y
					},
					m_Oil = 
					{
						m_Base = (ushort)float4.z
					}
				};
				m_Map[i] = value;
			}
		}
		return result;
	}
```


## Nested types

- `Game.Simulation.NaturalResourceSystem+RegenerateNaturalResourcesJob`  
- `Game.Simulation.NaturalResourceSystem+<>c`  
- `Game.Simulation.NaturalResourceSystem+<>c__DisplayClass21_0`  

