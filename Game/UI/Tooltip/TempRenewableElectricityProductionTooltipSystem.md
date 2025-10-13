# Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempRenewableElectricityProductionTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_ErrorQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Game.UI.Tooltip.ProgressTooltip m_Production;
    private Game.UI.Tooltip.StringTooltip m_WindWarning;
    private Game.UI.Tooltip.StringTooltip m_GroundWaterAvailabilityWarning;
    private Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem+TypeHandle __TypeHandle;

    public TempRenewableElectricityProductionTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_ErrorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ErrorQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Game.UI.Tooltip.ProgressTooltip m_Production`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_Production;
```

- `private Game.UI.Tooltip.StringTooltip m_WindWarning`  

```csharp
private Game.UI.Tooltip.StringTooltip m_WindWarning;
```

- `private Game.UI.Tooltip.StringTooltip m_GroundWaterAvailabilityWarning`  

```csharp
private Game.UI.Tooltip.StringTooltip m_GroundWaterAvailabilityWarning;
```

- `private Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempRenewableElectricityProductionTooltipSystem()`  

```csharp
[Preserve]
	public TempRenewableElectricityProductionTooltipSystem()
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
		m_WindSystem = base.World.GetOrCreateSystemManaged<WindSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_ErrorQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Error>());
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<RenewableElectricityProduction>(), ComponentType.Exclude<Deleted>());
		m_Production = new ProgressTooltip
		{
			path = "renewableElectricityProduction",
			icon = "Media/Game/Icons/Electricity.svg",
			label = LocalizedString.Id("Tools.ELECTRICITY_PRODUCTION_LABEL"),
			unit = "power",
			omitMax = true
		};
		m_WindWarning = new StringTooltip
		{
			path = "windWarning",
			value = LocalizedString.Id("Tools.WARNING[NotEnoughWind]"),
			color = TooltipColor.Warning
		};
		m_GroundWaterAvailabilityWarning = new StringTooltip
		{
			path = "groundWaterAvailabilityWarning",
			value = LocalizedString.Id("Tools.WARNING[NotEnoughGroundWater]"),
			color = TooltipColor.Warning
		};
		RequireForUpdate(m_TempQuery);
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
		if (!m_ErrorQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		CompleteDependency();
		float num = 0f;
		float num2 = 0f;
		bool flag = false;
		bool flag2 = false;
		JobHandle dependencies;
		NativeArray<Wind> map = m_WindSystem.GetMap(readOnly: true, out dependencies);
		JobHandle dependencies2;
		NativeArray<GroundWater> map2 = m_GroundWaterSystem.GetMap(readOnly: true, out dependencies2);
		dependencies.Complete();
		dependencies2.Complete();
		ComponentLookup<WindPoweredData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WindPoweredData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<GroundWaterPoweredData> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GroundWaterPoweredData_RO_ComponentLookup, ref base.CheckedStateRef);
		NativeArray<ArchetypeChunk> nativeArray = m_TempQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			ComponentTypeHandle<PrefabRef> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Transform> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Temp> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Game.Buildings.WaterPowered> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterPowered_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			foreach (ArchetypeChunk item in nativeArray)
			{
				NativeArray<PrefabRef> nativeArray2 = item.GetNativeArray(ref typeHandle);
				NativeArray<Transform> nativeArray3 = item.GetNativeArray(ref typeHandle2);
				NativeArray<Temp> nativeArray4 = item.GetNativeArray(ref typeHandle3);
				NativeArray<Game.Buildings.WaterPowered> nativeArray5 = item.GetNativeArray(ref typeHandle4);
				for (int i = 0; i < nativeArray2.Length; i++)
				{
					if ((nativeArray4[i].m_Flags & (TempFlags.Create | TempFlags.Modify | TempFlags.Upgrade)) == 0)
					{
						continue;
					}
					Entity prefab = nativeArray2[i].m_Prefab;
					if (componentLookup.HasComponent(prefab))
					{
						Wind wind = WindSystem.GetWind(nativeArray3[i].m_Position, map);
						float2 windProduction = PowerPlantAISystem.GetWindProduction(componentLookup[prefab], wind, 1f);
						num += windProduction.x;
						num2 += windProduction.y;
						flag |= windProduction.x < windProduction.y * 0.75f;
					}
					if (nativeArray5.Length != 0 && base.EntityManager.TryGetComponent<WaterPoweredData>(prefab, out var component))
					{
						Game.Buildings.WaterPowered waterPowered = nativeArray5[i];
						float waterCapacity = PowerPlantAISystem.GetWaterCapacity(waterPowered, component);
						float num3 = math.min(waterCapacity, waterPowered.m_Estimate * component.m_ProductionFactor);
						num += num3;
						num2 += waterCapacity;
					}
					if (componentLookup2.TryGetComponent(prefab, out var componentData) && componentData.m_MaximumGroundWater > 0)
					{
						float2 groundWaterProduction = PowerPlantAISystem.GetGroundWaterProduction(componentData, nativeArray3[i].m_Position, 1f, map2);
						num += groundWaterProduction.x;
						num2 += groundWaterProduction.y;
						if (groundWaterProduction.x < groundWaterProduction.y * 0.75f)
						{
							flag2 = true;
						}
					}
				}
			}
			if (num2 > 0f)
			{
				m_Production.value = num;
				m_Production.max = num2;
				ProgressTooltip.SetCapacityColor(m_Production);
				AddMouseTooltip(m_Production);
				if (flag)
				{
					AddMouseTooltip(m_WindWarning);
				}
				if (flag2)
				{
					AddMouseTooltip(m_GroundWaterAvailabilityWarning);
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```


## Nested types

- `Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem+TypeHandle`  

