# Game.UI.Tooltip.TempExtractorTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempExtractorTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Entities.EntityQuery m_ErrorQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Game.UI.Tooltip.StringTooltip m_ResourceAvailable;
    private Game.UI.Tooltip.StringTooltip m_ResourceUnavailable;
    private Game.UI.Tooltip.IntTooltip m_Surplus;
    private Game.UI.Tooltip.IntTooltip m_Deficit;
    private Game.UI.Tooltip.StringTooltip m_ClimateAvailable;
    private Game.UI.Tooltip.StringTooltip m_ClimateUnavailable;
    private Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle __TypeHandle;

    public TempExtractorTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean FindResource(Colossal.Mathematics.Circle2 circle, Game.Areas.MapFeature requiredFeature, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
    private System.Boolean FindWoodResource(Colossal.Mathematics.Circle2 circle);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Boolean ProcessAreaNodes(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodeBuf, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource);
    private System.Boolean ProcessAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource);
    private System.Boolean ShouldMapFeatureUseResourceIcon(Game.Economy.Resource resource);
}
```


## Fields

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Unity.Entities.EntityQuery m_ErrorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ErrorQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Game.UI.Tooltip.StringTooltip m_ResourceAvailable`  

```csharp
private Game.UI.Tooltip.StringTooltip m_ResourceAvailable;
```

- `private Game.UI.Tooltip.StringTooltip m_ResourceUnavailable`  

```csharp
private Game.UI.Tooltip.StringTooltip m_ResourceUnavailable;
```

- `private Game.UI.Tooltip.IntTooltip m_Surplus`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Surplus;
```

- `private Game.UI.Tooltip.IntTooltip m_Deficit`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Deficit;
```

- `private Game.UI.Tooltip.StringTooltip m_ClimateAvailable`  

```csharp
private Game.UI.Tooltip.StringTooltip m_ClimateAvailable;
```

- `private Game.UI.Tooltip.StringTooltip m_ClimateUnavailable`  

```csharp
private Game.UI.Tooltip.StringTooltip m_ClimateUnavailable;
```

- `private Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempExtractorTooltipSystem()`  

```csharp
[Preserve]
	public TempExtractorTooltipSystem()
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

- `private FindResource(Colossal.Mathematics.Circle2 circle, Game.Areas.MapFeature requiredFeature, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : System.Boolean`  

```csharp
private bool FindResource(Circle2 circle, MapFeature requiredFeature, CellMapData<NaturalResourceCell> resourceMap, DynamicBuffer<CityModifier> cityModifiers)
	{
		int2 cell = CellMapSystem<NaturalResourceCell>.GetCell(new float3(circle.position.x - circle.radius, 0f, circle.position.y - circle.radius), CellMapSystem<NaturalResourceCell>.kMapSize, resourceMap.m_TextureSize.x);
		int2 cell2 = CellMapSystem<NaturalResourceCell>.GetCell(new float3(circle.position.x + circle.radius, 0f, circle.position.y + circle.radius), CellMapSystem<NaturalResourceCell>.kMapSize, resourceMap.m_TextureSize.x);
		cell = math.max(new int2(0, 0), cell);
		cell2 = math.min(new int2(resourceMap.m_TextureSize.x - 1, resourceMap.m_TextureSize.y - 1), cell2);
		int2 cell3 = default(int2);
		cell3.x = cell.x;
		while (cell3.x <= cell2.x)
		{
			cell3.y = cell.y;
			while (cell3.y <= cell2.y)
			{
				if (MathUtils.Intersect(circle, CellMapSystem<NaturalResourceCell>.GetCellCenter(cell3, resourceMap.m_TextureSize.x).xz))
				{
					NaturalResourceCell naturalResourceCell = resourceMap.m_Buffer[cell3.x + cell3.y * resourceMap.m_TextureSize.x];
					float num = 0f;
					switch (requiredFeature)
					{
					case MapFeature.FertileLand:
						num = (int)naturalResourceCell.m_Fertility.m_Base;
						num -= (float)(int)naturalResourceCell.m_Fertility.m_Used;
						break;
					case MapFeature.Ore:
						num = (int)naturalResourceCell.m_Ore.m_Base;
						if (cityModifiers.IsCreated)
						{
							CityUtils.ApplyModifier(ref num, cityModifiers, CityModifierType.OreResourceAmount);
						}
						num -= (float)(int)naturalResourceCell.m_Ore.m_Used;
						break;
					case MapFeature.Oil:
						num = (int)naturalResourceCell.m_Oil.m_Base;
						if (cityModifiers.IsCreated)
						{
							CityUtils.ApplyModifier(ref num, cityModifiers, CityModifierType.OilResourceAmount);
						}
						num -= (float)(int)naturalResourceCell.m_Oil.m_Used;
						break;
					case MapFeature.Fish:
						num = (int)naturalResourceCell.m_Fish.m_Base;
						num -= (float)(int)naturalResourceCell.m_Fish.m_Used;
						break;
					default:
						num = 0f;
						break;
					}
					if (num > 0f)
					{
						return true;
					}
				}
				cell3.y++;
			}
			cell3.x++;
		}
		return false;
	}
```

- `private FindWoodResource(Colossal.Mathematics.Circle2 circle) : System.Boolean`  

```csharp
private bool FindWoodResource(Circle2 circle)
	{
		TreeIterator iterator = new TreeIterator
		{
			m_OverriddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TreeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Bounds = new Bounds2(circle.position - circle.radius, circle.position + circle.radius),
			m_Circle = circle,
			m_Result = 0f
		};
		JobHandle dependencies;
		NativeQuadTree<Entity, QuadTreeBoundsXZ> staticSearchTree = m_SearchSystem.GetStaticSearchTree(readOnly: true, out dependencies);
		dependencies.Complete();
		staticSearchTree.Iterate(ref iterator);
		return iterator.m_Result > 0f;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_IndustrialDemandSystem = base.World.GetOrCreateSystemManaged<IndustrialDemandSystem>();
		m_CountCompanyDataSystem = base.World.GetOrCreateSystemManaged<CountCompanyDataSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_ErrorQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Error>());
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Placeholder>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_ExtractorParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ExtractorParameterData>());
		m_ResourceAvailable = new StringTooltip
		{
			path = "extractorMapFeatureAvailable"
		};
		m_ResourceUnavailable = new StringTooltip
		{
			path = "extractorMapFeatureUnavailable",
			color = TooltipColor.Warning
		};
		m_ClimateAvailable = new StringTooltip
		{
			path = "extractorClimateAvailable",
			value = LocalizedString.Id("Tools.EXTRACTOR_CLIMATE_REQUIRED_AVAILABLE")
		};
		m_ClimateUnavailable = new StringTooltip
		{
			path = "extractorClimateUnavailable",
			value = LocalizedString.Id("Tools.EXTRACTOR_CLIMATE_REQUIRED_UNAVAILABLE"),
			color = TooltipColor.Warning
		};
		m_Surplus = new IntTooltip
		{
			path = "extractorCityProductionSurplus",
			label = LocalizedString.Id("Tools.EXTRACTOR_PRODUCTION_SURPLUS"),
			unit = "weightPerMonth"
		};
		m_Deficit = new IntTooltip
		{
			path = "extractorCityProductionDeficit",
			label = LocalizedString.Id("Tools.EXTRACTOR_PRODUCTION_DEFICIT"),
			unit = "weightPerMonth"
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
		if (!m_ErrorQuery.IsEmptyIgnoreFilter || !base.EntityManager.TryGetBuffer(m_CitySystem.City, isReadOnly: true, out DynamicBuffer<CityModifier> buffer))
		{
			return;
		}
		CompleteDependency();
		JobHandle dependencies;
		CellMapData<NaturalResourceCell> data = m_NaturalResourceSystem.GetData(readOnly: true, out dependencies);
		dependencies.Complete();
		ComponentLookup<PlaceholderBuildingData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderBuildingData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<BuildingPropertyData> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ExtractorAreaData> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<LotData> componentLookup4 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LotData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ResourceData> componentLookup5 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Transform> componentLookup6 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<PrefabRef> componentLookup7 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		BufferLookup<Game.Areas.SubArea> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef);
		BufferLookup<SubAreaNode> bufferLookup2 = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubAreaNode_RO_BufferLookup, ref base.CheckedStateRef);
		BufferLookup<InstalledUpgrade> bufferLookup3 = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef);
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		NativeArray<ArchetypeChunk> nativeArray = m_TempQuery.ToArchetypeChunkArray(Allocator.TempJob);
		MapFeature requiredFeature = MapFeature.None;
		bool foundResource = false;
		bool flag = false;
		Resource resource = Resource.NoResource;
		try
		{
			ComponentTypeHandle<Temp> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			dependencies.Complete();
			foreach (ArchetypeChunk item in nativeArray)
			{
				NativeArray<Entity> nativeArray2 = item.GetNativeArray(InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef));
				NativeArray<Temp> nativeArray3 = item.GetNativeArray(ref typeHandle);
				for (int i = 0; i < nativeArray2.Length; i++)
				{
					Entity entity = nativeArray2[i];
					if ((nativeArray3[i].m_Flags & (TempFlags.Create | TempFlags.Upgrade)) != 0)
					{
						Entity entity2 = componentLookup7[entity];
						if (componentLookup.HasComponent(entity2) && componentLookup2.HasComponent(entity2) && componentLookup[entity2].m_Type == BuildingType.ExtractorBuilding)
						{
							resource = componentLookup2[entity2].m_AllowedManufactured;
							DynamicBuffer<InstalledUpgrade> bufferData2;
							if (bufferLookup.TryGetBuffer(entity, out var bufferData) && ProcessAreas(bufferData, componentLookup3, componentLookup4, resource, prefabs, componentLookup5, componentLookup6[entity], data, buffer, ref requiredFeature, ref foundResource))
							{
								flag = true;
							}
							else if (bufferLookup3.TryGetBuffer(entity, out bufferData2))
							{
								for (int j = 0; j < bufferData2.Length; j++)
								{
									if (bufferLookup2.TryGetBuffer(componentLookup7[bufferData2[j].m_Upgrade], out var bufferData3) && bufferLookup.TryGetBuffer(bufferData2[j].m_Upgrade, out bufferData) && ProcessAreaNodes(bufferData, bufferData3, componentLookup3, componentLookup4, resource, prefabs, componentLookup5, componentLookup6[bufferData2[j].m_Upgrade], data, buffer, ref requiredFeature, ref foundResource))
									{
										flag = true;
									}
									else if (bufferLookup.TryGetBuffer(bufferData2[j].m_Upgrade, out bufferData) && ProcessAreas(bufferData, componentLookup3, componentLookup4, resource, prefabs, componentLookup5, componentLookup6[bufferData2[j].m_Upgrade], data, buffer, ref requiredFeature, ref foundResource))
									{
										flag = true;
									}
									if (flag)
									{
										break;
									}
								}
							}
						}
					}
					if (flag)
					{
						break;
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		if (!flag)
		{
			return;
		}
		JobHandle deps;
		NativeArray<int> production = m_CountCompanyDataSystem.GetProduction(out deps);
		JobHandle deps2;
		NativeArray<int> consumption = m_IndustrialDemandSystem.GetConsumption(out deps2);
		int resourceIndex = EconomyUtils.GetResourceIndex(resource);
		deps.Complete();
		deps2.Complete();
		int num = production[resourceIndex] - consumption[resourceIndex];
		Entity entity3 = prefabs[resource];
		ResourceData resourceData = componentLookup5[entity3];
		string icon = ImageSystem.GetIcon(m_PrefabSystem.GetPrefab<PrefabBase>(entity3));
		if (num > 0)
		{
			m_Surplus.value = num;
			m_Surplus.icon = icon;
			AddMouseTooltip(m_Surplus);
		}
		else
		{
			m_Deficit.value = -num;
			m_Deficit.icon = icon;
			AddMouseTooltip(m_Deficit);
		}
		bool flag2 = ShouldMapFeatureUseResourceIcon(resource);
		if (requiredFeature != MapFeature.None)
		{
			string mapFeatureIconName = AreaTools.GetMapFeatureIconName(requiredFeature);
			if (foundResource)
			{
				m_ResourceAvailable.icon = (flag2 ? icon : ("Media/Game/Icons/" + mapFeatureIconName + ".svg"));
				m_ResourceAvailable.value = LocalizedString.Id("Tools.EXTRACTOR_MAP_FEATURE_REQUIRED_AVAILABLE");
				AddMouseTooltip(m_ResourceAvailable);
			}
			else
			{
				m_ResourceUnavailable.icon = (flag2 ? icon : ("Media/Game/Icons/" + mapFeatureIconName + ".svg"));
				m_ResourceUnavailable.value = LocalizedString.Id("Tools.EXTRACTOR_MAP_FEATURE_REQUIRED_MISSING");
				AddMouseTooltip(m_ResourceUnavailable);
			}
		}
		if (resourceData.m_RequireTemperature)
		{
			if (m_ClimateSystem.averageTemperature >= resourceData.m_RequiredTemperature)
			{
				AddMouseTooltip(m_ClimateAvailable);
			}
			else
			{
				AddMouseTooltip(m_ClimateUnavailable);
			}
		}
	}
```

- `private ProcessAreaNodes(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodeBuf, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource) : System.Boolean`  

```csharp
private bool ProcessAreaNodes(DynamicBuffer<Game.Areas.SubArea> subAreas, DynamicBuffer<SubAreaNode> subAreaNodeBuf, ComponentLookup<ExtractorAreaData> extractorAreaDatas, ComponentLookup<LotData> lotDatas, Resource extractedResource, ResourcePrefabs resourcePrefabs, ComponentLookup<ResourceData> resourceDatas, Transform transform, CellMapData<NaturalResourceCell> resourceMap, DynamicBuffer<CityModifier> cityModifiers, ref MapFeature requiredFeature, ref bool foundResource)
	{
		bool result = false;
		float num = 0f;
		for (int i = 0; i < subAreaNodeBuf.Length; i++)
		{
			float num2 = ((math.abs(subAreaNodeBuf[i].m_Position.x) > math.abs(subAreaNodeBuf[i].m_Position.z)) ? math.abs(subAreaNodeBuf[i].m_Position.x) : math.abs(subAreaNodeBuf[i].m_Position.z));
			if (num2 > num)
			{
				num = num2;
			}
		}
		for (int j = 0; j < subAreas.Length; j++)
		{
			if (!base.EntityManager.TryGetComponent<PrefabRef>(subAreas[j].m_Area, out var component))
			{
				continue;
			}
			Entity prefab = component.m_Prefab;
			if (!extractorAreaDatas.HasComponent(prefab) || !lotDatas.HasComponent(prefab))
			{
				continue;
			}
			result = true;
			requiredFeature = ExtractorCompanySystem.GetRequiredMapFeature(extractedResource, prefab, resourcePrefabs, resourceDatas, extractorAreaDatas);
			if (requiredFeature != MapFeature.None)
			{
				float3 position = transform.m_Position;
				Circle2 circle = new Circle2(num, position.xz);
				if (requiredFeature == MapFeature.Forest)
				{
					foundResource = FindWoodResource(circle);
				}
				else
				{
					foundResource = FindResource(circle, requiredFeature, resourceMap, cityModifiers);
				}
			}
		}
		return result;
	}
```

- `private ProcessAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource) : System.Boolean`  

```csharp
private bool ProcessAreas(DynamicBuffer<Game.Areas.SubArea> subAreas, ComponentLookup<ExtractorAreaData> extractorAreaDatas, ComponentLookup<LotData> lotDatas, Resource extractedResource, ResourcePrefabs resourcePrefabs, ComponentLookup<ResourceData> resourceDatas, Transform transform, CellMapData<NaturalResourceCell> resourceMap, DynamicBuffer<CityModifier> cityModifiers, ref MapFeature requiredFeature, ref bool foundResource)
	{
		bool result = false;
		for (int i = 0; i < subAreas.Length; i++)
		{
			if (!base.EntityManager.TryGetComponent<PrefabRef>(subAreas[i].m_Area, out var component))
			{
				continue;
			}
			Entity prefab = component.m_Prefab;
			if (!extractorAreaDatas.HasComponent(prefab) || !lotDatas.HasComponent(prefab))
			{
				continue;
			}
			result = true;
			float maxRadius = lotDatas[prefab].m_MaxRadius;
			requiredFeature = ExtractorCompanySystem.GetRequiredMapFeature(extractedResource, prefab, resourcePrefabs, resourceDatas, extractorAreaDatas);
			if (requiredFeature != MapFeature.None)
			{
				float3 position = transform.m_Position;
				Circle2 circle = new Circle2(maxRadius, position.xz);
				if (requiredFeature == MapFeature.Forest)
				{
					foundResource = FindWoodResource(circle);
				}
				else
				{
					foundResource = FindResource(circle, requiredFeature, resourceMap, cityModifiers);
				}
			}
		}
		return result;
	}
```

- `private ShouldMapFeatureUseResourceIcon(Game.Economy.Resource resource) : System.Boolean`  

```csharp
private bool ShouldMapFeatureUseResourceIcon(Resource resource)
	{
		if (resource == Resource.Fish)
		{
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.UI.Tooltip.TempExtractorTooltipSystem+TreeIterator`  
- `Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle`  

