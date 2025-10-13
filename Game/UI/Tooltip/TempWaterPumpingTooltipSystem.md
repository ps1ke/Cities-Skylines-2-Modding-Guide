# Game.UI.Tooltip.TempWaterPumpingTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempWaterPumpingTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_ErrorQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_PumpQuery;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.UI.Tooltip.ProgressTooltip m_Capacity;
    private Game.UI.Tooltip.IntTooltip m_ReservoirUsage;
    private Game.UI.Tooltip.StringTooltip m_OverRefreshCapacityWarning;
    private Game.UI.Tooltip.StringTooltip m_AvailabilityWarning;
    private Game.UI.Localization.LocalizedString m_GroundWarning;
    private Game.UI.Localization.LocalizedString m_SurfaceWarning;
    private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult> m_TempResult;
    private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult;
    private Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle __TypeHandle;

    public TempWaterPumpingTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ProcessAvailabilityWarning(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp, Game.UI.Localization.LocalizedString warningText);
    private System.Void ProcessProduction(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp);
    private System.Void ProcessReservoir(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult reservoir);
    private System.Void ProcessResults();
}
```


## Fields

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_ErrorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ErrorQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_PumpQuery`  

```csharp
private Unity.Entities.EntityQuery m_PumpQuery;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.UI.Tooltip.ProgressTooltip m_Capacity`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_Capacity;
```

- `private Game.UI.Tooltip.IntTooltip m_ReservoirUsage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_ReservoirUsage;
```

- `private Game.UI.Tooltip.StringTooltip m_OverRefreshCapacityWarning`  

```csharp
private Game.UI.Tooltip.StringTooltip m_OverRefreshCapacityWarning;
```

- `private Game.UI.Tooltip.StringTooltip m_AvailabilityWarning`  

```csharp
private Game.UI.Tooltip.StringTooltip m_AvailabilityWarning;
```

- `private Game.UI.Localization.LocalizedString m_GroundWarning`  

```csharp
private Game.UI.Localization.LocalizedString m_GroundWarning;
```

- `private Game.UI.Localization.LocalizedString m_SurfaceWarning`  

```csharp
private Game.UI.Localization.LocalizedString m_SurfaceWarning;
```

- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult> m_TempResult`  

```csharp
private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult> m_TempResult;
```

- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult`  

```csharp
private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult;
```

- `private Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempWaterPumpingTooltipSystem()`  

```csharp
[Preserve]
	public TempWaterPumpingTooltipSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_ErrorQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Error>());
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.WaterPumpingStation>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Error>(), ComponentType.Exclude<Deleted>());
		m_PumpQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.WaterPumpingStation>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_ParameterQuery = GetEntityQuery(ComponentType.ReadOnly<WaterPipeParameterData>());
		m_Capacity = new ProgressTooltip
		{
			path = "groundWaterCapacity",
			icon = "Media/Game/Icons/Water.svg",
			label = LocalizedString.Id("Tools.WATER_OUTPUT_LABEL"),
			unit = "volume",
			omitMax = true
		};
		m_ReservoirUsage = new IntTooltip
		{
			path = "groundWaterReservoirUsage",
			label = LocalizedString.Id("Tools.GROUND_WATER_RESERVOIR_USAGE"),
			unit = "percentage"
		};
		m_OverRefreshCapacityWarning = new StringTooltip
		{
			path = "groundWaterOverRefreshCapacityWarning",
			value = LocalizedString.Id("Tools.WARNING[OverRefreshCapacity]"),
			color = TooltipColor.Warning
		};
		m_AvailabilityWarning = new StringTooltip
		{
			path = "waterAvailabilityWarning",
			color = TooltipColor.Warning
		};
		m_GroundWarning = LocalizedString.Id("Tools.WARNING[NotEnoughGroundWater]");
		m_SurfaceWarning = LocalizedString.Id("Tools.WARNING[NotEnoughFreshWater]");
		m_TempResult = new NativeReference<TempResult>(Allocator.Persistent);
		m_ReservoirResult = new NativeReference<GroundWaterReservoirResult>(Allocator.Persistent);
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
		m_TempResult.Dispose();
		m_ReservoirResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_ErrorQuery.IsEmptyIgnoreFilter || m_TempQuery.IsEmptyIgnoreFilter)
		{
			m_TempResult.Value = default(TempResult);
			m_ReservoirResult.Value = default(GroundWaterReservoirResult);
			return;
		}
		ProcessResults();
		m_TempResult.Value = default(TempResult);
		m_ReservoirResult.Value = default(GroundWaterReservoirResult);
		JobHandle dependencies;
		NativeArray<GroundWater> map = m_GroundWaterSystem.GetMap(readOnly: true, out dependencies);
		WaterPipeParameterData singleton = m_ParameterQuery.GetSingleton<WaterPipeParameterData>();
		JobHandle deps;
		JobHandle jobHandle = JobChunkExtensions.Schedule(new TempJob
		{
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PumpDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterPumpingStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterSources = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterSourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GroundWaterMap = map,
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_Result = m_TempResult,
			m_Parameters = singleton
		}, m_TempQuery, JobHandle.CombineDependencies(base.Dependency, dependencies, deps));
		m_WaterSystem.AddSurfaceReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		NativeParallelHashMap<int2, int> pumpCapacityMap = new NativeParallelHashMap<int2, int>(8, Allocator.TempJob);
		NativeList<int2> tempGroundWaterPumpCells = new NativeList<int2>(Allocator.TempJob);
		JobHandle dependsOn = JobChunkExtensions.Schedule(new GroundWaterPumpJob
		{
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PumpDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterPumpingStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GroundWaterMap = map,
			m_PumpCapacityMap = pumpCapacityMap,
			m_TempGroundWaterPumpCells = tempGroundWaterPumpCells,
			m_Parameters = singleton
		}, m_PumpQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		GroundWaterReservoirJob jobData = new GroundWaterReservoirJob
		{
			m_GroundWaterMap = map,
			m_PumpCapacityMap = pumpCapacityMap,
			m_TempGroundWaterPumpCells = tempGroundWaterPumpCells,
			m_Queue = new NativeQueue<int2>(Allocator.TempJob),
			m_Result = m_ReservoirResult
		};
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData, dependsOn);
		jobData.m_Queue.Dispose(jobHandle2);
		pumpCapacityMap.Dispose(jobHandle2);
		tempGroundWaterPumpCells.Dispose(jobHandle2);
		base.Dependency = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		m_GroundWaterSystem.AddReader(base.Dependency);
	}
```

- `private ProcessAvailabilityWarning(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp, Game.UI.Localization.LocalizedString warningText) : System.Void`  

```csharp
private void ProcessAvailabilityWarning(TempResult temp, LocalizedString warningText)
	{
		if (temp.m_Production > 0 && (float)temp.m_Production < (float)temp.m_MaxCapacity * 0.75f)
		{
			m_AvailabilityWarning.value = warningText;
			AddMouseTooltip(m_AvailabilityWarning);
		}
	}
```

- `private ProcessProduction(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp) : System.Void`  

```csharp
private void ProcessProduction(TempResult temp)
	{
		if (temp.m_Production > 0)
		{
			m_Capacity.value = temp.m_Production;
			m_Capacity.max = temp.m_MaxCapacity;
			ProgressTooltip.SetCapacityColor(m_Capacity);
			AddMouseTooltip(m_Capacity);
		}
	}
```

- `private ProcessReservoir(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult reservoir) : System.Void`  

```csharp
private void ProcessReservoir(GroundWaterReservoirResult reservoir)
	{
		WaterPipeParameterData singleton = m_ParameterQuery.GetSingleton<WaterPipeParameterData>();
		float num = singleton.m_GroundwaterReplenish / singleton.m_GroundwaterUsageMultiplier * (float)reservoir.m_Volume;
		float num2 = ((num > 0f && reservoir.m_PumpCapacity > 0) ? math.clamp(100f * (float)reservoir.m_PumpCapacity / num, 1f, 999f) : 0f);
		m_ReservoirUsage.value = Mathf.RoundToInt(num2);
		m_ReservoirUsage.color = ((num2 > 100f) ? TooltipColor.Warning : TooltipColor.Info);
		AddMouseTooltip(m_ReservoirUsage);
		if (num2 > 100f)
		{
			AddMouseTooltip(m_OverRefreshCapacityWarning);
		}
	}
```

- `private ProcessResults() : System.Void`  

```csharp
private void ProcessResults()
	{
		TempResult value = m_TempResult.Value;
		GroundWaterReservoirResult value2 = m_ReservoirResult.Value;
		if (value.m_MaxCapacity <= 0)
		{
			return;
		}
		if ((value.m_Types & AllowedWaterTypes.Groundwater) != AllowedWaterTypes.None)
		{
			ProcessProduction(value);
			if (value2.m_Volume > 0)
			{
				ProcessReservoir(value2);
			}
			ProcessAvailabilityWarning(value, m_GroundWarning);
		}
		else if ((value.m_Types & AllowedWaterTypes.SurfaceWater) != AllowedWaterTypes.None)
		{
			ProcessProduction(value);
			ProcessAvailabilityWarning(value, m_SurfaceWarning);
		}
		else
		{
			ProcessProduction(value);
		}
	}
```


## Nested types

- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterPumpJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle`  

