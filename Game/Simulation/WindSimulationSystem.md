# Game.Simulation.WindSimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public class WindSimulationSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Mathematics.float2 <constantWind>k__BackingField;
    private System.Single <m_ConstantPressure>k__BackingField;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private System.Boolean m_Odd;
    private Unity.Jobs.JobHandle m_Deps;
    private Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> m_Cells;
    public static readonly System.Int32 kUpdateInterval;
    public static readonly Unity.Mathematics.int3 kResolution;
    public static readonly System.Single kChangeFactor;
    public static readonly System.Single kTerrainSlowdown;
    public static readonly System.Single kAirSlowdown;
    public static readonly System.Single kVerticalSlowdown;

    public Unity.Mathematics.float2 constantWind { get; set; }
    private System.Single m_ConstantPressure { private get; private set; }

    public WindSimulationSystem();

    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Byte[] CreateByteArray<T>(Unity.Collections.NativeArray<T> src);
    public System.Void DebugLoad();
    public System.Void DebugSave();
    public System.Void Deserialize<TReader>(TReader reader);
    private Game.Simulation.WindSimulationSystem+WindCell GetCell(Unity.Mathematics.int3 position);
    public static Game.Simulation.WindSimulationSystem+WindCell GetCell(Unity.Mathematics.int3 position, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> GetCells(Unity.Jobs.JobHandle& deps);
    public static Unity.Mathematics.float3 GetCenterVelocity(Unity.Mathematics.int3 cell, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Void SetWind(Unity.Mathematics.float2 direction, System.Single pressure);
}
```


## Fields

- `private Unity.Mathematics.float2 <constantWind>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <constantWind>k__BackingField;
```

- `private System.Single <m_ConstantPressure>k__BackingField`  

```csharp
private System.Single <m_ConstantPressure>k__BackingField;
```

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

- `private System.Boolean m_Odd`  

```csharp
private System.Boolean m_Odd;
```

- `private Unity.Jobs.JobHandle m_Deps`  

```csharp
private Unity.Jobs.JobHandle m_Deps;
```

- `private Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> m_Cells`  

```csharp
private Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> m_Cells;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```

- `public static readonly Unity.Mathematics.int3 kResolution`  

```csharp
public static readonly Unity.Mathematics.int3 kResolution;
```

- `public static readonly System.Single kChangeFactor`  

```csharp
public static readonly System.Single kChangeFactor;
```

- `public static readonly System.Single kTerrainSlowdown`  

```csharp
public static readonly System.Single kTerrainSlowdown;
```

- `public static readonly System.Single kAirSlowdown`  

```csharp
public static readonly System.Single kAirSlowdown;
```

- `public static readonly System.Single kVerticalSlowdown`  

```csharp
public static readonly System.Single kVerticalSlowdown;
```


## Properties

- `public Unity.Mathematics.float2 constantWind { get; set }`  

```csharp
public Unity.Mathematics.float2 constantWind { get; set; }
```

- `private System.Single m_ConstantPressure { private get; private set }`  

```csharp
private System.Single m_ConstantPressure { private get; private set; }
```


## Constructors

- `public WindSimulationSystem()`  

```csharp
[Preserve]
	public WindSimulationSystem()
	{
	}
```


## Methods

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public void AddReader(JobHandle reader)
	{
		m_Deps = JobHandle.CombineDependencies(m_Deps, reader);
	}
```

- `public CreateByteArray<T>(Unity.Collections.NativeArray<T> src) : System.Byte[]`  

```csharp
public System.Byte[] CreateByteArray<T>(Unity.Collections.NativeArray<T> src);
```

- `public DebugLoad() : System.Void`  

```csharp
public unsafe void DebugLoad()
	{
		m_Deps.Complete();
		using System.IO.BinaryReader binaryReader = new System.IO.BinaryReader(File.OpenRead(Application.streamingAssetsPath + "/wind_temp.dat"));
		int num = binaryReader.ReadInt32();
		int num2 = binaryReader.ReadInt32();
		int num3 = binaryReader.ReadInt32();
		int num4 = num * num2 * num3 * UnsafeUtility.SizeOf<WindCell>();
		byte[] array = new byte[num4];
		binaryReader.Read(array, 0, num * num2 * num3 * sizeof(WindCell));
		byte* unsafePtr = (byte*)m_Cells.GetUnsafePtr();
		for (int i = 0; i < num4; i++)
		{
			unsafePtr[i] = array[i];
		}
	}
```

- `public DebugSave() : System.Void`  

```csharp
public void DebugSave()
	{
		m_Deps.Complete();
		using System.IO.BinaryWriter binaryWriter = new System.IO.BinaryWriter(File.OpenWrite(Application.streamingAssetsPath + "/wind_temp.dat"));
		binaryWriter.Write(kResolution.x);
		binaryWriter.Write(kResolution.y);
		binaryWriter.Write(kResolution.z);
		binaryWriter.Write(CreateByteArray(m_Cells));
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private GetCell(Unity.Mathematics.int3 position) : Game.Simulation.WindSimulationSystem+WindCell`  

```csharp
public static WindCell GetCell(int3 position, NativeArray<WindCell> cells)
	{
		int num = position.x + position.y * kResolution.x + position.z * kResolution.x * kResolution.y;
		if (num < 0 || num >= cells.Length)
		{
			return default(WindCell);
		}
		return cells[num];
	}
```

- `public static GetCell(Unity.Mathematics.int3 position, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells) : Game.Simulation.WindSimulationSystem+WindCell`  

```csharp
public static WindCell GetCell(int3 position, NativeArray<WindCell> cells)
	{
		int num = position.x + position.y * kResolution.x + position.z * kResolution.x * kResolution.y;
		if (num < 0 || num >= cells.Length)
		{
			return default(WindCell);
		}
		return cells[num];
	}
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		int3 @int = new int3(index % kResolution.x, index / kResolution.x % kResolution.y, index / (kResolution.x * kResolution.y));
		float3 result = CellMapSystem<Wind>.kMapSize * new float3(((float)@int.x + 0.5f) / (float)kResolution.x, 0f, ((float)@int.y + 0.5f) / (float)kResolution.y) - CellMapSystem<Wind>.kMapSize / 2;
		result.y = 100f + 1024f * ((float)@int.z + 0.5f) / (float)kResolution.z;
		return result;
	}
```

- `public GetCells(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell>`  

```csharp
public NativeArray<WindCell> GetCells(out JobHandle deps)
	{
		deps = m_Deps;
		return m_Cells;
	}
```

- `public static GetCenterVelocity(Unity.Mathematics.int3 cell, Unity.Collections.NativeArray<Game.Simulation.WindSimulationSystem+WindCell> cells) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCenterVelocity(int3 cell, NativeArray<WindCell> cells)
	{
		float3 velocities = GetCell(cell, cells).m_Velocities;
		float3 @float = ((cell.x > 0) ? GetCell(cell + new int3(-1, 0, 0), cells).m_Velocities : velocities);
		float3 float2 = ((cell.y > 0) ? GetCell(cell + new int3(0, -1, 0), cells).m_Velocities : velocities);
		float3 float3 = ((cell.z > 0) ? GetCell(cell + new int3(0, 0, -1), cells).m_Velocities : velocities);
		return 0.5f * new float3(velocities.x + @float.x, velocities.y + float2.y, velocities.z + float3.z);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		if (phase != SystemUpdatePhase.GameSimulation)
		{
			return 1;
		}
		return kUpdateInterval;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		constantWind = new float2(0.275f, 0.275f);
		m_ConstantPressure = 40f;
		m_Cells = new NativeArray<WindCell>(kResolution.x * kResolution.y * kResolution.z, Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Cells.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_TerrainSystem.heightmap != null)
		{
			m_Odd = !m_Odd;
			if (!m_Odd)
			{
				TerrainHeightData data = m_TerrainSystem.GetHeightData();
				float x = TerrainUtils.ToWorldSpace(ref data, 0f);
				float y = TerrainUtils.ToWorldSpace(ref data, 65535f);
				float2 terrainRange = new float2(x, y);
				JobHandle deps;
				UpdateWindVelocityJob jobData = new UpdateWindVelocityJob
				{
					m_Cells = m_Cells,
					m_TerrainHeightData = data,
					m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
					m_TerrainRange = terrainRange
				};
				m_Deps = jobData.Schedule(kResolution.x * kResolution.y * kResolution.z, JobHandle.CombineDependencies(m_Deps, deps, base.Dependency));
				m_WaterSystem.AddSurfaceReader(m_Deps);
				m_TerrainSystem.AddCPUHeightReader(m_Deps);
			}
			else
			{
				UpdatePressureJob jobData2 = new UpdatePressureJob
				{
					m_Cells = m_Cells,
					m_Wind = constantWind / 10f
				};
				m_Deps = jobData2.Schedule(kResolution.x * kResolution.y * kResolution.z, JobHandle.CombineDependencies(m_Deps, base.Dependency));
			}
			base.Dependency = m_Deps;
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_Deps.Complete();
		for (int i = 0; i < m_Cells.Length; i++)
		{
			m_Cells[i] = new WindCell
			{
				m_Pressure = m_ConstantPressure,
				m_Velocities = new float3(constantWind, 0f)
			};
		}
	}
```

- `public SetWind(Unity.Mathematics.float2 direction, System.Single pressure) : System.Void`  

```csharp
public void SetWind(float2 direction, float pressure)
	{
		m_Deps.Complete();
		constantWind = direction;
		m_ConstantPressure = pressure;
		SetDefaults(default(Context));
	}
```


## Nested types

- `Game.Simulation.WindSimulationSystem+WindCell`  
- `Game.Simulation.WindSimulationSystem+UpdateWindVelocityJob`  
- `Game.Simulation.WindSimulationSystem+UpdatePressureJob`  

