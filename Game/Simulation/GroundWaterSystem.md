# Game.Simulation.GroundWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.GroundWater>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GroundWaterSystem : Game.Simulation.CellMapSystem<Game.Simulation.GroundWater>, Colossal.Serialization.Entities.IJobSerializable
{
    private Unity.Entities.EntityQuery m_ParameterQuery;
    public static readonly System.Int32 kTextureSize;
    public static const System.Int32 kMaxGroundWater;
    public static const System.Int32 kMinGroundWaterThreshold;

    public GroundWaterSystem();

    internal static System.Void <ConsumeGroundWater>g__ConsumeFraction|9_0(Game.Simulation.GroundWater& gw, System.Single cellAvailable, Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0& );
    private static System.Single Bilinear(System.Int16 v00, System.Int16 v10, System.Int16 v01, System.Int16 v11, System.Single sx, System.Single sy);
    public static System.Void ConsumeGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, System.Int32 amount);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.GroundWater GetGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap);
    private static Game.Simulation.GroundWater GetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    public static System.Boolean IsValidCell(Unity.Mathematics.int2 cell);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
    private static System.Void SetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell, Game.Simulation.GroundWater gw);
    public static System.Boolean TryGetCell(Unity.Mathematics.float3 position, Unity.Mathematics.int2& cell);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static const System.Int32 kMaxGroundWater`  

```csharp
public static const System.Int32 kMaxGroundWater;
```

- `public static const System.Int32 kMinGroundWaterThreshold`  

```csharp
public static const System.Int32 kMinGroundWaterThreshold;
```


## Constructors

- `public GroundWaterSystem()`  

```csharp
[Preserve]
	public GroundWaterSystem()
	{
	}
```


## Methods

- `internal static <ConsumeGroundWater>g__ConsumeFraction|9_0(Game.Simulation.GroundWater& gw, System.Single cellAvailable, Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0& ) : System.Void`  

```csharp
internal static System.Void <ConsumeGroundWater>g__ConsumeFraction|9_0(Game.Simulation.GroundWater& gw, System.Single cellAvailable, Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0& );
```

- `private static Bilinear(System.Int16 v00, System.Int16 v10, System.Int16 v01, System.Int16 v11, System.Single sx, System.Single sy) : System.Single`  

```csharp
private static float Bilinear(short v00, short v10, short v01, short v11, float sx, float sy)
	{
		return math.lerp(math.lerp(v00, v10, sx), math.lerp(v01, v11, sx), sy);
	}
```

- `public static ConsumeGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, System.Int32 amount) : System.Void`  

```csharp
public static void ConsumeGroundWater(float3 position, NativeArray<GroundWater> groundWaterMap, int amount)
	{
		Assert.IsTrue(amount >= 0);
		float2 @float = CellMapSystem<GroundWater>.GetCellCoords(position, CellMapSystem<GroundWater>.kMapSize, kTextureSize) - new float2(0.5f, 0.5f);
		int2 cell = new int2(Mathf.FloorToInt(@float.x), Mathf.FloorToInt(@float.y));
		int2 cell2 = new int2(cell.x + 1, cell.y);
		int2 cell3 = new int2(cell.x, cell.y + 1);
		int2 cell4 = new int2(cell.x + 1, cell.y + 1);
		GroundWater gw = GetGroundWater(groundWaterMap, cell);
		GroundWater gw2 = GetGroundWater(groundWaterMap, cell2);
		GroundWater gw3 = GetGroundWater(groundWaterMap, cell3);
		GroundWater gw4 = GetGroundWater(groundWaterMap, cell4);
		float sx = @float.x - (float)cell.x;
		float sy = @float.y - (float)cell.y;
		float num = math.ceil(Bilinear(gw.m_Amount, 0, 0, 0, sx, sy));
		float num2 = math.ceil(Bilinear(0, gw2.m_Amount, 0, 0, sx, sy));
		float num3 = math.ceil(Bilinear(0, 0, gw3.m_Amount, 0, sx, sy));
		float num4 = math.ceil(Bilinear(0, 0, 0, gw4.m_Amount, sx, sy));
		float totalAvailable = num + num2 + num3 + num4;
		float totalConsumed = math.min(amount, totalAvailable);
		if (totalAvailable < (float)amount)
		{
			UnityEngine.Debug.LogWarning($"Trying to consume more groundwater than available! amount: {amount}, available: {totalAvailable}");
		}
		ConsumeFraction(ref gw, num);
		ConsumeFraction(ref gw2, num2);
		ConsumeFraction(ref gw3, num3);
		ConsumeFraction(ref gw4, num4);
		Assert.IsTrue(Mathf.Approximately(totalAvailable, 0f));
		Assert.IsTrue(Mathf.Approximately(totalConsumed, 0f));
		SetGroundWater(groundWaterMap, cell, gw);
		SetGroundWater(groundWaterMap, cell2, gw2);
		SetGroundWater(groundWaterMap, cell3, gw3);
		SetGroundWater(groundWaterMap, cell4, gw4);
		void ConsumeFraction(ref GroundWater reference, float cellAvailable)
		{
			if (!(totalAvailable < 0.5f))
			{
				float num5 = cellAvailable / totalAvailable;
				totalAvailable -= cellAvailable;
				float num6 = math.max(y: math.max(0f, totalConsumed - totalAvailable), x: math.round(num5 * totalConsumed));
				Assert.IsTrue(num6 <= (float)reference.m_Amount);
				reference.Consume((int)num6);
				totalConsumed -= num6;
			}
		}
	}
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<GroundWater>.GetCellCenter(index, kTextureSize);
	}
```

- `public static GetGroundWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap) : Game.Simulation.GroundWater`  

```csharp
private static GroundWater GetGroundWater(NativeArray<GroundWater> groundWaterMap, int2 cell)
	{
		if (!IsValidCell(cell))
		{
			return default(GroundWater);
		}
		return groundWaterMap[cell.x + kTextureSize * cell.y];
	}
```

- `private static GetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell) : Game.Simulation.GroundWater`  

```csharp
private static GroundWater GetGroundWater(NativeArray<GroundWater> groundWaterMap, int2 cell)
	{
		if (!IsValidCell(cell))
		{
			return default(GroundWater);
		}
		return groundWaterMap[cell.x + kTextureSize * cell.y];
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 128;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 64;
	}
```

- `public static IsValidCell(Unity.Mathematics.int2 cell) : System.Boolean`  

```csharp
public static bool IsValidCell(int2 cell)
	{
		if (cell.x >= 0 && cell.y >= 0 && cell.x < kTextureSize)
		{
			return cell.y < kTextureSize;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		CreateTextures(kTextureSize);
		m_ParameterQuery = GetEntityQuery(ComponentType.ReadOnly<WaterPipeParameterData>());
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		GroundWaterTickJob jobData = new GroundWaterTickJob
		{
			m_GroundWaterMap = m_Map,
			m_Parameters = m_ParameterQuery.GetSingleton<WaterPipeParameterData>()
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies, base.Dependency));
		AddWriter(base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
	}
```

- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle SetDefaults(Context context)
	{
		if (context.purpose == Purpose.NewGame && context.version < Version.timoSerializationFlow)
		{
			for (int i = 0; i < m_Map.Length; i++)
			{
				float num = (float)(i % kTextureSize) / (float)kTextureSize;
				float num2 = (float)(i / kTextureSize) / (float)kTextureSize;
				short num3 = (short)Mathf.RoundToInt(10000f * math.saturate((Mathf.PerlinNoise(32f * num, 32f * num2) - 0.6f) / 0.4f));
				GroundWater value = new GroundWater
				{
					m_Amount = num3,
					m_Max = num3
				};
				m_Map[i] = value;
			}
			return default(JobHandle);
		}
		return base.SetDefaults(context);
	}
```

- `private static SetGroundWater(Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Mathematics.int2 cell, Game.Simulation.GroundWater gw) : System.Void`  

```csharp
private static void SetGroundWater(NativeArray<GroundWater> groundWaterMap, int2 cell, GroundWater gw)
	{
		if (IsValidCell(cell))
		{
			groundWaterMap[cell.x + kTextureSize * cell.y] = gw;
		}
	}
```

- `public static TryGetCell(Unity.Mathematics.float3 position, Unity.Mathematics.int2& cell) : System.Boolean`  

```csharp
public static bool TryGetCell(float3 position, out int2 cell)
	{
		cell = CellMapSystem<GroundWater>.GetCell(position, CellMapSystem<GroundWater>.kMapSize, kTextureSize);
		return IsValidCell(cell);
	}
```


## Nested types

- `Game.Simulation.GroundWaterSystem+GroundWaterTickJob`  
- `Game.Simulation.GroundWaterSystem+<>c__DisplayClass9_0`  

