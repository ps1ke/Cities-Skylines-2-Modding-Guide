# Game.Simulation.GraduationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GraduationSystem : Game.GameSystemBase
{
    public System.Int32 debugFastGraduationLevel;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityQuery m_StudentQuery;
    private Game.Simulation.GraduationSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1855827631_0;
    private Unity.Entities.EntityQuery __query_1855827631_1;
    public static const System.Int32 kUpdatesPerDay;
    public static const System.Int32 kCheckSlowdown;

    public GraduationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetDropoutProbability(Game.Citizens.Citizen citizen, System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData& economyParameters, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single efficiency, Game.Common.TimeData timeData);
    public static System.Single GetDropoutProbability(System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.Single age, System.Single studyWillingness, System.Int32 failedEducationCount, System.Single graduationProbability, Game.Prefabs.EconomyParameterData& economyParameters);
    public static System.Single GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single studyWillingness, System.Single efficiency);
    public static System.Single GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, System.Single graduationModifier, Unity.Mathematics.float2 collegeModifier, Unity.Mathematics.float2 uniModifier, System.Single studyWillingness, System.Single efficiency);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public System.Int32 debugFastGraduationLevel`  

```csharp
public System.Int32 debugFastGraduationLevel;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityQuery m_StudentQuery`  

```csharp
private Unity.Entities.EntityQuery m_StudentQuery;
```

- `private Game.Simulation.GraduationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.GraduationSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1855827631_0`  

```csharp
private Unity.Entities.EntityQuery __query_1855827631_0;
```

- `private Unity.Entities.EntityQuery __query_1855827631_1`  

```csharp
private Unity.Entities.EntityQuery __query_1855827631_1;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```

- `public static const System.Int32 kCheckSlowdown`  

```csharp
public static const System.Int32 kCheckSlowdown;
```


## Constructors

- `public GraduationSystem()`  

```csharp
[Preserve]
	public GraduationSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<EconomyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1855827631_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<TimeData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1855827631_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public static GetDropoutProbability(Game.Citizens.Citizen citizen, System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData& economyParameters, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single efficiency, Game.Common.TimeData timeData) : System.Single`  

```csharp
public static float GetDropoutProbability(int level, float commute, float fee, int wealth, float age, float studyWillingness, int failedEducationCount, float graduationProbability, ref EconomyParameterData economyParameters)
	{
		int num = 4 - failedEducationCount;
		float t = math.pow(1f - graduationProbability, num);
		float num2 = 1f / (graduationProbability * 2f * 1f);
		float num3 = num2 * fee;
		if (level > 2)
		{
			num3 -= num2 * (float)economyParameters.m_UnemploymentBenefit;
		}
		float num4 = math.max(0f, (float)AgingSystem.GetElderAgeLimitInDays() - age);
		float num5 = (float)economyParameters.GetWage(math.min(2, level - 1)) * num4;
		float num6 = math.lerp(economyParameters.GetWage(level), economyParameters.GetWage(level - 1), t) * (num4 - num2) - num3 + (0.5f + studyWillingness) * (float)economyParameters.m_UnemploymentBenefit * num2;
		if (num5 < num6)
		{
			float num7 = (num6 - num5) / num5;
			return math.saturate(-0.1f + (float)level / 4f - 10f * num7 - (float)wealth / (num6 - num5) + commute / 5000f);
		}
		return 1f;
	}
```

- `public static GetDropoutProbability(System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.Single age, System.Single studyWillingness, System.Int32 failedEducationCount, System.Single graduationProbability, Game.Prefabs.EconomyParameterData& economyParameters) : System.Single`  

```csharp
public static float GetDropoutProbability(int level, float commute, float fee, int wealth, float age, float studyWillingness, int failedEducationCount, float graduationProbability, ref EconomyParameterData economyParameters)
	{
		int num = 4 - failedEducationCount;
		float t = math.pow(1f - graduationProbability, num);
		float num2 = 1f / (graduationProbability * 2f * 1f);
		float num3 = num2 * fee;
		if (level > 2)
		{
			num3 -= num2 * (float)economyParameters.m_UnemploymentBenefit;
		}
		float num4 = math.max(0f, (float)AgingSystem.GetElderAgeLimitInDays() - age);
		float num5 = (float)economyParameters.GetWage(math.min(2, level - 1)) * num4;
		float num6 = math.lerp(economyParameters.GetWage(level), economyParameters.GetWage(level - 1), t) * (num4 - num2) - num3 + (0.5f + studyWillingness) * (float)economyParameters.m_UnemploymentBenefit * num2;
		if (num5 < num6)
		{
			float num7 = (num6 - num5) / num5;
			return math.saturate(-0.1f + (float)level / 4f - 10f * num7 - (float)wealth / (num6 - num5) + commute / 5000f);
		}
		return 1f;
	}
```

- `public static GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single studyWillingness, System.Single efficiency) : System.Single`  

```csharp
public static float GetGraduationProbability(int level, int wellbeing, float graduationModifier, float2 collegeModifier, float2 uniModifier, float studyWillingness, float efficiency)
	{
		if (efficiency <= 0.001f)
		{
			return 0f;
		}
		float num = math.saturate((0.5f + studyWillingness) * (float)wellbeing / 75f);
		float num2 = 0f;
		switch (level)
		{
		case 1:
			num2 = math.smoothstep(0f, 1f, 0.6f * num + 0.41f);
			break;
		case 2:
			num2 = 0.6f * math.log(2.6f * num + 1.1f);
			break;
		case 3:
			num2 = 90f * math.log(1.6f * num + 1f);
			num2 += collegeModifier.x;
			num2 += num2 * collegeModifier.y;
			num2 /= 100f;
			break;
		case 4:
			num2 = 70f * num;
			num2 += uniModifier.x;
			num2 += num2 * uniModifier.y;
			num2 /= 100f;
			break;
		default:
			num2 = 0f;
			break;
		}
		num2 = 1f - (1f - num2) / efficiency;
		return num2 + graduationModifier;
	}
```

- `public static GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, System.Single graduationModifier, Unity.Mathematics.float2 collegeModifier, Unity.Mathematics.float2 uniModifier, System.Single studyWillingness, System.Single efficiency) : System.Single`  

```csharp
public static float GetGraduationProbability(int level, int wellbeing, float graduationModifier, float2 collegeModifier, float2 uniModifier, float studyWillingness, float efficiency)
	{
		if (efficiency <= 0.001f)
		{
			return 0f;
		}
		float num = math.saturate((0.5f + studyWillingness) * (float)wellbeing / 75f);
		float num2 = 0f;
		switch (level)
		{
		case 1:
			num2 = math.smoothstep(0f, 1f, 0.6f * num + 0.41f);
			break;
		case 2:
			num2 = 0.6f * math.log(2.6f * num + 1.1f);
			break;
		case 3:
			num2 = 90f * math.log(1.6f * num + 1f);
			num2 += collegeModifier.x;
			num2 += num2 * collegeModifier.y;
			num2 /= 100f;
			break;
		case 4:
			num2 = 70f * num;
			num2 += uniModifier.x;
			num2 += num2 * uniModifier.y;
			num2 /= 100f;
			break;
		default:
			num2 = 0f;
			break;
		}
		num2 = 1f - (1f - num2) / efficiency;
		return num2 + graduationModifier;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16384;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_StudentQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Citizens.Student>(), ComponentType.ReadWrite<Citizen>(), ComponentType.ReadOnly<UpdateFrame>());
		RequireForUpdate(m_StudentQuery);
		RequireForUpdate<EconomyParameterData>();
		RequireForUpdate<TimeData>();
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, 1, 16);
		GraduationJob jobData = new GraduationJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StudentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SchoolDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SchoolData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_Purposes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingEfficiencies = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
			m_Fees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter(),
			m_EconomyParameters = __query_1855827631_0.GetSingleton<EconomyParameterData>(),
			m_TimeData = __query_1855827631_1.GetSingleton<TimeData>(),
			m_RandomSeed = RandomSeed.Next(),
			m_City = m_CitySystem.City,
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_UpdateFrameIndex = updateFrame,
			m_DebugFastGraduationLevel = debugFastGraduationLevel
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_StudentQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.GraduationSystem+GraduationJob`  
- `Game.Simulation.GraduationSystem+TypeHandle`  

