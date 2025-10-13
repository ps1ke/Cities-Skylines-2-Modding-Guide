# Game.Simulation.BuildingPollutionAddSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingPollutionAddSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_PolluterQuery;
    private Unity.Collections.NativeArray<System.Single> m_GroundWeightCache;
    private Unity.Collections.NativeArray<System.Single> m_AirWeightCache;
    private Unity.Collections.NativeArray<System.Single> m_NoiseWeightCache;
    private Unity.Collections.NativeArray<System.Single> m_DistanceWeightCache;
    private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_GroundPollutionQueue;
    private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_AirPollutionQueue;
    private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_NoisePollutionQueue;
    private Game.Simulation.BuildingPollutionAddSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_985639355_0;
    public static readonly System.Int32 kUpdatesPerDay;

    public BuildingPollutionAddSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void CountRenters(System.Int32& count, System.Int32& education, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, System.Boolean ignoreEmployees);
    public static Game.Prefabs.PollutionData GetBuildingPollution(Unity.Entities.Entity prefab, System.Boolean destroyed, System.Boolean abandoned, System.Boolean isPark, System.Single efficiency, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Game.Prefabs.PollutionParameterData pollutionParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionModifierData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionModifierDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    private static System.Single GetWeight(System.Single distance, System.Single exponent);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_PolluterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolluterQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_GroundWeightCache`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_GroundWeightCache;
```

- `private Unity.Collections.NativeArray<System.Single> m_AirWeightCache`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_AirWeightCache;
```

- `private Unity.Collections.NativeArray<System.Single> m_NoiseWeightCache`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_NoiseWeightCache;
```

- `private Unity.Collections.NativeArray<System.Single> m_DistanceWeightCache`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_DistanceWeightCache;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_GroundPollutionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_GroundPollutionQueue;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_AirPollutionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_AirPollutionQueue;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_NoisePollutionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_NoisePollutionQueue;
```

- `private Game.Simulation.BuildingPollutionAddSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BuildingPollutionAddSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_985639355_0`  

```csharp
private Unity.Entities.EntityQuery __query_985639355_0;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public BuildingPollutionAddSystem()`  

```csharp
[Preserve]
	public BuildingPollutionAddSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<PollutionParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_985639355_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private static CountRenters(System.Int32& count, System.Int32& education, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, System.Boolean ignoreEmployees) : System.Void`  

```csharp
private static void CountRenters(out int count, out int education, DynamicBuffer<Renter> renters, ref BufferLookup<Employee> employees, ref BufferLookup<HouseholdCitizen> householdCitizens, ref ComponentLookup<Citizen> citizens, bool ignoreEmployees)
	{
		count = 0;
		education = 0;
		foreach (Renter item in renters)
		{
			if (householdCitizens.TryGetBuffer(item, out var bufferData))
			{
				foreach (HouseholdCitizen item2 in bufferData)
				{
					if (citizens.TryGetComponent(item2, out var componentData))
					{
						education += componentData.GetEducationLevel();
						count++;
					}
				}
			}
			else
			{
				if (ignoreEmployees || !employees.TryGetBuffer(item, out var bufferData2))
				{
					continue;
				}
				foreach (Employee item3 in bufferData2)
				{
					if (citizens.TryGetComponent(item3.m_Worker, out var componentData2))
					{
						education += componentData2.GetEducationLevel();
						count++;
					}
				}
			}
		}
	}
```

- `public static GetBuildingPollution(Unity.Entities.Entity prefab, System.Boolean destroyed, System.Boolean abandoned, System.Boolean isPark, System.Single efficiency, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Game.Prefabs.PollutionParameterData pollutionParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionModifierData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionModifierDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : Game.Prefabs.PollutionData`  

```csharp
public static PollutionData GetBuildingPollution(Entity prefab, bool destroyed, bool abandoned, bool isPark, float efficiency, DynamicBuffer<Renter> renters, DynamicBuffer<InstalledUpgrade> installedUpgrades, PollutionParameterData pollutionParameters, DynamicBuffer<CityModifier> cityModifiers, ref ComponentLookup<PrefabRef> prefabRefs, ref ComponentLookup<BuildingData> buildingDatas, ref ComponentLookup<SpawnableBuildingData> spawnableDatas, ref ComponentLookup<PollutionData> pollutionDatas, ref ComponentLookup<PollutionModifierData> pollutionModifierDatas, ref ComponentLookup<ZoneData> zoneDatas, ref BufferLookup<Employee> employees, ref BufferLookup<HouseholdCitizen> householdCitizens, ref ComponentLookup<Citizen> citizens)
	{
		PollutionData componentData;
		if (!(destroyed || abandoned))
		{
			if (efficiency > 0f && pollutionDatas.TryGetComponent(prefab, out componentData))
			{
				if (installedUpgrades.IsCreated)
				{
					UpgradeUtils.CombineStats(ref componentData, installedUpgrades, ref prefabRefs, ref pollutionDatas);
				}
				SpawnableBuildingData componentData2;
				if (componentData.m_ScaleWithRenters && !isPark && renters.IsCreated)
				{
					CountRenters(out var count, out var education, renters, ref employees, ref householdCitizens, ref citizens, ignoreEmployees: false);
					float num = (spawnableDatas.TryGetComponent(prefab, out componentData2) ? ((float)(int)componentData2.m_Level) : 5f);
					float num2 = ((count > 0) ? (5f * (float)count / (num + 0.5f * (float)(education / count))) : 0f);
					componentData.m_GroundPollution *= num2;
					componentData.m_AirPollution *= num2;
					componentData.m_NoisePollution *= num2;
				}
				if (cityModifiers.IsCreated && spawnableDatas.TryGetComponent(prefab, out componentData2))
				{
					ZoneData zoneData = zoneDatas[componentData2.m_ZonePrefab];
					if (zoneData.m_AreaType == AreaType.Industrial && (zoneData.m_ZoneFlags & ZoneFlags.Office) == 0)
					{
						CityUtils.ApplyModifier(ref componentData.m_GroundPollution, cityModifiers, CityModifierType.IndustrialGroundPollution);
						CityUtils.ApplyModifier(ref componentData.m_AirPollution, cityModifiers, CityModifierType.IndustrialAirPollution);
					}
				}
				if (installedUpgrades.IsCreated)
				{
					PollutionModifierData data = default(PollutionModifierData);
					UpgradeUtils.CombineStats(ref data, installedUpgrades, ref prefabRefs, ref pollutionModifierDatas);
					componentData.m_GroundPollution *= math.max(0f, 1f + data.m_GroundPollutionMultiplier);
					componentData.m_AirPollution *= math.max(0f, 1f + data.m_AirPollutionMultiplier);
					componentData.m_NoisePollution *= math.max(0f, 1f + data.m_NoisePollutionMultiplier);
				}
			}
			else
			{
				componentData = default(PollutionData);
			}
		}
		else
		{
			BuildingData buildingData = buildingDatas[prefab];
			componentData = new PollutionData
			{
				m_GroundPollution = 0f,
				m_AirPollution = 0f,
				m_NoisePollution = (destroyed ? 0f : (5f * (float)(buildingData.m_LotSize.x * buildingData.m_LotSize.y) * pollutionParameters.m_AbandonedNoisePollutionMultiplier))
			};
		}
		if ((abandoned || isPark) && renters.IsCreated)
		{
			CountRenters(out var count2, out var _, renters, ref employees, ref householdCitizens, ref citizens, ignoreEmployees: true);
			componentData.m_NoisePollution += count2 * pollutionParameters.m_HomelessNoisePollution;
		}
		return componentData;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (16 * kUpdatesPerDay);
	}
```

- `private static GetWeight(System.Single distance, System.Single exponent) : System.Single`  

```csharp
private static float GetWeight(float distance, float exponent)
	{
		return 1f / math.max(20f, math.pow(distance, exponent));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_GroundPollutionQueue = new NativeQueue<PollutionItem>(Allocator.Persistent);
		m_AirPollutionQueue = new NativeQueue<PollutionItem>(Allocator.Persistent);
		m_NoisePollutionQueue = new NativeQueue<PollutionItem>(Allocator.Persistent);
		m_PolluterQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Placeholder>());
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		if (m_GroundWeightCache.IsCreated)
		{
			m_GroundWeightCache.Dispose();
		}
		if (m_AirWeightCache.IsCreated)
		{
			m_AirWeightCache.Dispose();
		}
		if (m_NoiseWeightCache.IsCreated)
		{
			m_NoiseWeightCache.Dispose();
		}
		if (m_DistanceWeightCache.IsCreated)
		{
			m_DistanceWeightCache.Dispose();
		}
		m_GroundPollutionQueue.Dispose();
		m_AirPollutionQueue.Dispose();
		m_NoisePollutionQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		PollutionParameterData singleton = __query_985639355_0.GetSingleton<PollutionParameterData>();
		float num = math.max(math.max(singleton.m_GroundRadius, singleton.m_AirRadius), singleton.m_NoiseRadius);
		num *= num;
		if (!m_GroundWeightCache.IsCreated)
		{
			int num2 = 3 + Mathf.CeilToInt(2f * singleton.m_GroundRadius * (float)GroundPollutionSystem.kTextureSize / (float)CellMapSystem<GroundPollution>.kMapSize);
			m_GroundWeightCache = new NativeArray<float>(num2 * num2, Allocator.Persistent);
			num2 = 3 + Mathf.CeilToInt(2f * singleton.m_AirRadius * (float)AirPollutionSystem.kTextureSize / (float)CellMapSystem<AirPollution>.kMapSize);
			m_AirWeightCache = new NativeArray<float>(num2 * num2, Allocator.Persistent);
			num2 = 3 + Mathf.CeilToInt(2f * singleton.m_NoiseRadius * (float)NoisePollutionSystem.kTextureSize / (float)CellMapSystem<NoisePollution>.kMapSize);
			m_NoiseWeightCache = new NativeArray<float>(num2 * num2, Allocator.Persistent);
			m_DistanceWeightCache = new NativeArray<float>(256, Allocator.Persistent);
			for (int i = 0; i < 256; i++)
			{
				m_DistanceWeightCache[i] = GetWeight(math.sqrt(num * (float)i / 256f), singleton.m_DistanceExponent);
			}
		}
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new BuildingPolluteJob
		{
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AbandonedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingEfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PollutionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PollutionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PollutionModifierDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PollutionModifierData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Employees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_PollutionParameters = singleton,
			m_GroundPollutionQueue = m_GroundPollutionQueue.AsParallelWriter(),
			m_AirPollutionQueue = m_AirPollutionQueue.AsParallelWriter(),
			m_NoisePollutionQueue = m_NoisePollutionQueue.AsParallelWriter(),
			m_City = m_CitySystem.City,
			m_UpdateFrameIndex = updateFrameWithInterval
		}, m_PolluterQuery, base.Dependency);
		JobHandle dependencies;
		JobHandle jobHandle2 = IJobExtensions.Schedule(new ApplyBuildingPollutionJob<GroundPollution>
		{
			m_PollutionMap = m_GroundPollutionSystem.GetMap(readOnly: false, out dependencies),
			m_MapSize = CellMapSystem<GroundPollution>.kMapSize,
			m_TextureSize = GroundPollutionSystem.kTextureSize,
			m_PollutionParameters = singleton,
			m_MaxRadiusSq = num,
			m_Radius = singleton.m_GroundRadius,
			m_PollutionQueue = m_GroundPollutionQueue,
			m_WeightCache = m_GroundWeightCache,
			m_DistanceWeightCache = m_DistanceWeightCache,
			m_Multiplier = singleton.m_GroundMultiplier
		}, JobHandle.CombineDependencies(jobHandle, dependencies));
		m_GroundPollutionSystem.AddWriter(jobHandle2);
		JobHandle dependencies2;
		JobHandle jobHandle3 = IJobExtensions.Schedule(new ApplyBuildingPollutionJob<AirPollution>
		{
			m_PollutionMap = m_AirPollutionSystem.GetMap(readOnly: false, out dependencies2),
			m_MapSize = CellMapSystem<AirPollution>.kMapSize,
			m_TextureSize = AirPollutionSystem.kTextureSize,
			m_PollutionParameters = singleton,
			m_MaxRadiusSq = num,
			m_Radius = singleton.m_AirRadius,
			m_PollutionQueue = m_AirPollutionQueue,
			m_WeightCache = m_AirWeightCache,
			m_DistanceWeightCache = m_DistanceWeightCache,
			m_Multiplier = singleton.m_AirMultiplier
		}, JobHandle.CombineDependencies(dependencies2, jobHandle));
		m_AirPollutionSystem.AddWriter(jobHandle3);
		JobHandle dependencies3;
		JobHandle jobHandle4 = IJobExtensions.Schedule(new ApplyBuildingPollutionJob<NoisePollution>
		{
			m_PollutionMap = m_NoisePollutionSystem.GetMap(readOnly: false, out dependencies3),
			m_MapSize = CellMapSystem<NoisePollution>.kMapSize,
			m_TextureSize = NoisePollutionSystem.kTextureSize,
			m_PollutionParameters = singleton,
			m_MaxRadiusSq = num,
			m_Radius = singleton.m_NoiseRadius,
			m_PollutionQueue = m_NoisePollutionQueue,
			m_WeightCache = m_NoiseWeightCache,
			m_DistanceWeightCache = m_DistanceWeightCache,
			m_Multiplier = singleton.m_NoiseMultiplier
		}, JobHandle.CombineDependencies(dependencies3, jobHandle));
		m_NoisePollutionSystem.AddWriter(jobHandle4);
		base.Dependency = JobHandle.CombineDependencies(jobHandle2, jobHandle3, jobHandle4);
	}
```


## Nested types

- `Game.Simulation.BuildingPollutionAddSystem+PollutionItem`  
- `Game.Simulation.BuildingPollutionAddSystem+ApplyBuildingPollutionJob<T>`  
- `Game.Simulation.BuildingPollutionAddSystem+BuildingPolluteJob`  
- `Game.Simulation.BuildingPollutionAddSystem+TypeHandle`  

