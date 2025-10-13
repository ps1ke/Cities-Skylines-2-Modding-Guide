# Game.UI.Tooltip.TerrainToolTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TerrainToolTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.TerrainToolSystem m_TerrainTool;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.UI.Tooltip.IntTooltip m_GroundwaterVolume;
    private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult;

    public TerrainToolTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ProcessResults();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.TerrainToolSystem m_TerrainTool`  

```csharp
private Game.Tools.TerrainToolSystem m_TerrainTool;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_GroundwaterVolume`  

```csharp
private Game.UI.Tooltip.IntTooltip m_GroundwaterVolume;
```

- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult`  

```csharp
private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult;
```


## Constructors

- `public TerrainToolTooltipSystem()`  

```csharp
[Preserve]
	public TerrainToolTooltipSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_TerrainTool = base.World.GetOrCreateSystemManaged<TerrainToolSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_ParameterQuery = GetEntityQuery(ComponentType.ReadOnly<WaterPipeParameterData>());
		RequireForUpdate(m_ParameterQuery);
		m_GroundwaterVolume = new IntTooltip
		{
			path = "groundWaterCapacity",
			icon = "Media/Game/Icons/Water.svg",
			label = LocalizedString.Id("Tools.GROUNDWATER_VOLUME"),
			unit = "volume"
		};
		m_ReservoirResult = new NativeReference<TempWaterPumpingTooltipSystem.GroundWaterReservoirResult>(Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_ReservoirResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ToolSystem.activeTool == m_TerrainTool && m_TerrainTool.prefab != null && m_TerrainTool.prefab.m_Target == TerraformingTarget.GroundWater && m_ToolRaycastSystem.GetRaycastResult(out var result))
		{
			ProcessResults();
			m_ReservoirResult.Value = default(TempWaterPumpingTooltipSystem.GroundWaterReservoirResult);
			if (GroundWaterSystem.TryGetCell(result.m_Hit.m_HitPosition, out var cell))
			{
				JobHandle dependencies;
				NativeArray<GroundWater> map = m_GroundWaterSystem.GetMap(readOnly: true, out dependencies);
				NativeList<int2> tempGroundWaterPumpCells = new NativeList<int2>(1, Allocator.TempJob) { in cell };
				TempWaterPumpingTooltipSystem.GroundWaterReservoirJob jobData = new TempWaterPumpingTooltipSystem.GroundWaterReservoirJob
				{
					m_GroundWaterMap = map,
					m_PumpCapacityMap = new NativeParallelHashMap<int2, int>(0, Allocator.TempJob),
					m_TempGroundWaterPumpCells = tempGroundWaterPumpCells,
					m_Queue = new NativeQueue<int2>(Allocator.TempJob),
					m_Result = m_ReservoirResult
				};
				base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, dependencies));
				jobData.m_Queue.Dispose(base.Dependency);
				jobData.m_PumpCapacityMap.Dispose(base.Dependency);
				tempGroundWaterPumpCells.Dispose(base.Dependency);
				m_GroundWaterSystem.AddReader(base.Dependency);
			}
		}
		else
		{
			m_ReservoirResult.Value = default(TempWaterPumpingTooltipSystem.GroundWaterReservoirResult);
		}
	}
```

- `private ProcessResults() : System.Void`  

```csharp
private void ProcessResults()
	{
		TempWaterPumpingTooltipSystem.GroundWaterReservoirResult value = m_ReservoirResult.Value;
		if (value.m_Volume > 0)
		{
			WaterPipeParameterData singleton = m_ParameterQuery.GetSingleton<WaterPipeParameterData>();
			float f = singleton.m_GroundwaterReplenish / singleton.m_GroundwaterUsageMultiplier * (float)value.m_Volume;
			m_GroundwaterVolume.value = Mathf.RoundToInt(f);
			if (m_GroundwaterVolume.value > 0)
			{
				AddMouseTooltip(m_GroundwaterVolume);
			}
		}
	}
```


