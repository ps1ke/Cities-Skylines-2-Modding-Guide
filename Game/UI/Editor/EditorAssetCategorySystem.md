# Game.UI.Editor.EditorAssetCategorySystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EditorAssetCategorySystem : Game.GameSystemBase
{
    private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_Categories;
    private System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.EditorAssetCategory> m_PathMap;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_ServiceQuery;
    private Unity.Entities.EntityQuery m_ZoneQuery;
    private Unity.Entities.EntityQuery m_ThemeQuery;
    private Unity.Entities.EntityQuery m_Overrides;
    private Unity.Entities.EntityQuery m_PrefabModificationQuery;
    private System.Boolean m_Dirty;
    private Game.UI.Editor.EditorAssetCategorySystem+TypeHandle __TypeHandle;

    public EditorAssetCategorySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddCategory(Game.UI.Editor.EditorAssetCategory category, Game.UI.Editor.EditorAssetCategory parent);
    private System.Void AddOverrides();
    private System.Void ClearCategories();
    private Game.UI.Editor.EditorAssetCategory CreateCategory(System.String path);
    private System.Void GenerateAreaCategories();
    private System.Void GenerateBridgeCategory();
    private System.Void GenerateBuildingCategories();
    private System.Void GenerateBushCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateCategories();
    private System.Void GenerateCharacterCategories();
    private System.Void GenerateEffectCategories();
    private System.Void GenerateFoliageCategories();
    private System.Void GenerateIndustrialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateLocationCategories();
    private System.Void GenerateMiscBuildingCategory(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GeneratePropCategories();
    private System.Void GeneratePublicTransportVehicleCategory(Game.Prefabs.TransportType transportType, Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateResidentialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateRoadCategory();
    private System.Void GenerateServiceBuildingCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateServiceVehicleCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateSpawnableBuildingCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateSurfaceCategories();
    private System.Void GenerateTrackCategories();
    private System.Void GenerateTrackTypeCategory(Game.Net.TrackTypes trackTypes, Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateTreeCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateVehicleCategories();
    private System.Void GenerateZoneCategories(Game.Zones.AreaType areaType, System.Boolean office, Game.UI.Editor.EditorAssetCategory parent);
    public System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> GetCategories(System.Boolean ignoreEmpty);
    private System.Collections.Generic.IEnumerable<System.ValueTuple<Game.UI.Editor.EditorAssetCategory, System.Int32>> GetCategoriesImpl(System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> categories, System.Int32 level, System.Boolean ignoreEmpty);
    public System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>> GetHierarchy(System.Boolean ignoreEmpty);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_Categories`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_Categories;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.EditorAssetCategory> m_PathMap`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.EditorAssetCategory> m_PathMap;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_ServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceQuery;
```

- `private Unity.Entities.EntityQuery m_ZoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ZoneQuery;
```

- `private Unity.Entities.EntityQuery m_ThemeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ThemeQuery;
```

- `private Unity.Entities.EntityQuery m_Overrides`  

```csharp
private Unity.Entities.EntityQuery m_Overrides;
```

- `private Unity.Entities.EntityQuery m_PrefabModificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabModificationQuery;
```

- `private System.Boolean m_Dirty`  

```csharp
private System.Boolean m_Dirty;
```

- `private Game.UI.Editor.EditorAssetCategorySystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.EditorAssetCategorySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EditorAssetCategorySystem()`  

```csharp
[Preserve]
	public EditorAssetCategorySystem()
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

- `private AddCategory(Game.UI.Editor.EditorAssetCategory category, Game.UI.Editor.EditorAssetCategory parent = null) : System.Void`  

```csharp
private void AddCategory(EditorAssetCategory category, EditorAssetCategory parent = null)
	{
		string text = category.id.Trim('/');
		category.path = ((parent != null) ? (parent.path + "/" + text) : text);
		if (parent == null)
		{
			m_Categories.Add(category);
		}
		else
		{
			parent.AddSubCategory(category);
		}
		m_PathMap[category.path] = category;
	}
```

- `private AddOverrides() : System.Void`  

```csharp
private void AddOverrides()
	{
		NativeArray<Entity> nativeArray = m_Overrides.ToEntityArray(Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (!m_PrefabSystem.TryGetPrefab<PrefabBase>(nativeArray[i], out var prefab))
			{
				continue;
			}
			EditorAssetCategoryOverride component = prefab.GetComponent<EditorAssetCategoryOverride>();
			if (component.m_IncludeCategories != null)
			{
				for (int j = 0; j < component.m_IncludeCategories.Length; j++)
				{
					string text = component.m_IncludeCategories[j];
					if (m_PathMap.TryGetValue(text, out var value))
					{
						value.AddEntity(nativeArray[i]);
					}
					else
					{
						CreateCategory(text).AddEntity(nativeArray[i]);
					}
				}
			}
			if (component.m_ExcludeCategories == null)
			{
				continue;
			}
			for (int k = 0; k < component.m_ExcludeCategories.Length; k++)
			{
				string key = component.m_ExcludeCategories[k];
				if (m_PathMap.TryGetValue(key, out var value2))
				{
					value2.AddExclusion(nativeArray[i]);
				}
			}
		}
	}
```

- `private ClearCategories() : System.Void`  

```csharp
private void ClearCategories()
	{
		m_Categories.Clear();
		m_PathMap.Clear();
	}
```

- `private CreateCategory(System.String path) : Game.UI.Editor.EditorAssetCategory`  

```csharp
private EditorAssetCategory CreateCategory(string path)
	{
		string[] array = path.Split("/");
		EditorAssetCategory editorAssetCategory = null;
		string text = null;
		for (int i = 0; i < array.Length; i++)
		{
			text = ((text != null) ? string.Join("/", text, array[i]) : array[i]);
			if (m_PathMap.TryGetValue(text, out var value))
			{
				editorAssetCategory = value;
				continue;
			}
			EditorAssetCategory editorAssetCategory2 = new EditorAssetCategory
			{
				id = array[i]
			};
			AddCategory(editorAssetCategory2, editorAssetCategory);
			editorAssetCategory = editorAssetCategory2;
		}
		return editorAssetCategory;
	}
```

- `private GenerateAreaCategories() : System.Void`  

```csharp
private void GenerateAreaCategories()
	{
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Areas",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<AreaData>(), ComponentType.Exclude<SurfaceData>())
		};
		AddCategory(category);
	}
```

- `private GenerateBridgeCategory() : System.Void`  

```csharp
private void GenerateBridgeCategory()
	{
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Bridges",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<BridgeData>()),
			icon = "Media/Game/Icons/CableStayed.svg"
		};
		AddCategory(category);
	}
```

- `private GenerateBuildingCategories() : System.Void`  

```csharp
private void GenerateBuildingCategories()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Buildings",
			entityQuery = GetEntityQuery(new EntityQueryDesc
			{
				Any = new ComponentType[2]
				{
					ComponentType.ReadOnly<BuildingData>(),
					ComponentType.ReadOnly<BuildingExtensionData>()
				}
			}),
			includeChildCategories = false
		};
		AddCategory(editorAssetCategory);
		GenerateServiceBuildingCategories(editorAssetCategory);
		GenerateSpawnableBuildingCategories(editorAssetCategory);
		GenerateMiscBuildingCategory(editorAssetCategory);
	}
```

- `private GenerateBushCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateBushCategories(EditorAssetCategory parent)
	{
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Bushes",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<PlantData>(), ComponentType.Exclude<TreeData>())
		};
		AddCategory(category, parent);
	}
```

- `private GenerateCategories() : System.Void`  

```csharp
private void GenerateCategories()
	{
		ClearCategories();
		GenerateBuildingCategories();
		GenerateVehicleCategories();
		GeneratePropCategories();
		GenerateFoliageCategories();
		GenerateCharacterCategories();
		GenerateAreaCategories();
		GenerateSurfaceCategories();
		GenerateBridgeCategory();
		GenerateRoadCategory();
		GenerateTrackCategories();
		GenerateEffectCategories();
		GenerateLocationCategories();
		AddOverrides();
		m_Dirty = false;
	}
```

- `private GenerateCharacterCategories() : System.Void`  

```csharp
private void GenerateCharacterCategories()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Characters",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<CreatureData>()),
			includeChildCategories = false
		};
		AddCategory(editorAssetCategory);
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "People",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<HumanData>())
		};
		AddCategory(category, editorAssetCategory);
		EditorAssetCategory editorAssetCategory2 = new EditorAssetCategory
		{
			id = "Animals",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<AnimalData>())
		};
		AddCategory(editorAssetCategory2, editorAssetCategory);
		EditorAssetCategory category2 = new EditorAssetCategory
		{
			id = "Pets",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<PetData>())
		};
		AddCategory(category2, editorAssetCategory2);
		EditorAssetCategory category3 = new EditorAssetCategory
		{
			id = "Livestock",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<DomesticatedData>())
		};
		AddCategory(category3, editorAssetCategory2);
		EditorAssetCategory category4 = new EditorAssetCategory
		{
			id = "Wildlife",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<WildlifeData>())
		};
		AddCategory(category4, editorAssetCategory2);
	}
```

- `private GenerateEffectCategories() : System.Void`  

```csharp
private void GenerateEffectCategories()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Effects",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<EffectData>())
		};
		AddCategory(editorAssetCategory);
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "VFX",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<EffectData>(), ComponentType.ReadOnly<VFXData>())
		};
		AddCategory(category, editorAssetCategory);
		EditorAssetCategory category2 = new EditorAssetCategory
		{
			id = "Audio",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<EffectData>(), ComponentType.ReadOnly<AudioEffectData>())
		};
		AddCategory(category2, editorAssetCategory);
		EditorAssetCategory category3 = new EditorAssetCategory
		{
			id = "Lights",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<EffectData>(), ComponentType.ReadOnly<LightEffectData>())
		};
		AddCategory(category3, editorAssetCategory);
	}
```

- `private GenerateFoliageCategories() : System.Void`  

```csharp
private void GenerateFoliageCategories()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Foliage",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<PlantData>()),
			icon = "Media/Game/Icons/Vegetation.svg",
			includeChildCategories = false
		};
		AddCategory(editorAssetCategory);
		GenerateTreeCategories(editorAssetCategory);
		GenerateBushCategories(editorAssetCategory);
	}
```

- `private GenerateIndustrialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateIndustrialVehicleCategory(EditorAssetCategory parent)
	{
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Industrial",
			entityQuery = GetEntityQuery(new EntityQueryDesc
			{
				All = new ComponentType[1] { ComponentType.ReadOnly<VehicleData>() },
				Any = new ComponentType[3]
				{
					ComponentType.ReadOnly<CargoTransportVehicleData>(),
					ComponentType.ReadOnly<DeliveryTruckData>(),
					ComponentType.ReadOnly<WorkVehicleData>()
				}
			}),
			icon = "Media/Game/Icons/ZoneIndustrial.svg"
		};
		AddCategory(category, parent);
	}
```

- `private GenerateLocationCategories() : System.Void`  

```csharp
private void GenerateLocationCategories()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Locations"
		};
		AddCategory(editorAssetCategory);
		EditorAssetCategory editorAssetCategory2 = new EditorAssetCategory
		{
			id = "Spawners"
		};
		AddCategory(editorAssetCategory2, editorAssetCategory);
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Animals",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<CreatureSpawnData>())
		};
		AddCategory(category, editorAssetCategory2);
		EditorAssetCategory category2 = new EditorAssetCategory
		{
			id = "Vehicles",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<TrafficSpawnerData>())
		};
		AddCategory(category2, editorAssetCategory2);
	}
```

- `private GenerateMiscBuildingCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateMiscBuildingCategory(EditorAssetCategory parent)
	{
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Misc",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingData>(), ComponentType.Exclude<ServiceObjectData>(), ComponentType.Exclude<SpawnableBuildingData>(), ComponentType.Exclude<SignatureBuildingData>(), ComponentType.Exclude<ServiceUpgradeBuilding>(), ComponentType.Exclude<ExtractorFacilityData>())
		};
		AddCategory(category, parent);
	}
```

- `private GeneratePropCategories() : System.Void`  

```csharp
private void GeneratePropCategories()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Props",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<StaticObjectData>(), ComponentType.Exclude<BuildingData>(), ComponentType.Exclude<NetObjectData>(), ComponentType.Exclude<BuildingExtensionData>(), ComponentType.Exclude<PillarData>(), ComponentType.Exclude<PlantData>(), ComponentType.Exclude<BrandObjectData>()),
			includeChildCategories = false
		};
		AddCategory(editorAssetCategory);
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Brand Graphics",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<StaticObjectData>(), ComponentType.ReadOnly<BrandObjectData>(), ComponentType.Exclude<BuildingData>(), ComponentType.Exclude<NetObjectData>(), ComponentType.Exclude<BuildingExtensionData>(), ComponentType.Exclude<PillarData>(), ComponentType.Exclude<PlantData>())
		};
		AddCategory(category, editorAssetCategory);
	}
```

- `private GeneratePublicTransportVehicleCategory(Game.Prefabs.TransportType transportType, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GeneratePublicTransportVehicleCategory(TransportType transportType, EditorAssetCategory parent)
	{
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = transportType.ToString(),
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<VehicleData>(), ComponentType.ReadOnly<PublicTransportVehicleData>()),
			icon = $"Media/Game/Icons/{transportType}.svg",
			filter = new PublicTransportTypeFilter
			{
				m_TransportType = transportType,
				m_Purpose = PublicTransportPurpose.TransportLine
			}
		};
		AddCategory(category, parent);
	}
```

- `private GenerateResidentialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateResidentialVehicleCategory(EditorAssetCategory parent)
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Residential"
		};
		AddCategory(editorAssetCategory, parent);
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Cars",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<VehicleData>(), ComponentType.ReadOnly<PersonalCarData>()),
			filter = new PassengerCountFilter
			{
				m_Type = PassengerCountFilter.FilterType.NotEquals,
				m_Count = 1
			},
			icon = "Media/Game/Icons/GenericVehicle.svg"
		};
		AddCategory(category, editorAssetCategory);
		EditorAssetCategory category2 = new EditorAssetCategory
		{
			id = "Bikes",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<VehicleData>(), ComponentType.ReadOnly<PersonalCarData>()),
			filter = new PassengerCountFilter
			{
				m_Type = PassengerCountFilter.FilterType.Equals,
				m_Count = 1
			},
			icon = "Media/Game/Icons/Bicycle.svg"
		};
		AddCategory(category2, editorAssetCategory);
	}
```

- `private GenerateRoadCategory() : System.Void`  

```csharp
private void GenerateRoadCategory()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Roads"
		};
		AddCategory(editorAssetCategory);
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Roads",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<RoadData>(), ComponentType.Exclude<BridgeData>()),
			icon = "Media/Game/Icons/Roads.svg"
		};
		AddCategory(category, editorAssetCategory);
		EditorAssetCategory category2 = new EditorAssetCategory
		{
			id = "Intersections",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<AssetStampData>(), ComponentType.ReadOnly<Game.Prefabs.SubNet>())
		};
		AddCategory(category2, editorAssetCategory);
	}
```

- `private GenerateServiceBuildingCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateServiceBuildingCategories(EditorAssetCategory parent)
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Services"
		};
		AddCategory(editorAssetCategory, parent);
		NativeArray<Entity> nativeArray = m_ServiceQuery.ToEntityArray(Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (m_PrefabSystem.TryGetPrefab<PrefabBase>(nativeArray[i], out var prefab))
			{
				EditorAssetCategory category = new EditorAssetCategory
				{
					id = prefab.name,
					entityQuery = GetEntityQuery(new EntityQueryDesc
					{
						All = new ComponentType[2]
						{
							ComponentType.ReadOnly<BuildingData>(),
							ComponentType.ReadOnly<ServiceObjectData>()
						},
						None = new ComponentType[1] { ComponentType.ReadOnly<TrafficSpawnerData>() }
					}, new EntityQueryDesc
					{
						All = new ComponentType[1] { ComponentType.ReadOnly<ServiceUpgradeBuilding>() },
						Any = new ComponentType[2]
						{
							ComponentType.ReadOnly<BuildingData>(),
							ComponentType.ReadOnly<BuildingExtensionData>()
						},
						None = new ComponentType[1] { ComponentType.ReadOnly<TrafficSpawnerData>() }
					}),
					filter = new ServiceTypeFilter(nativeArray[i]),
					icon = ImageSystem.GetIcon(prefab)
				};
				AddCategory(category, editorAssetCategory);
			}
		}
	}
```

- `private GenerateServiceVehicleCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateServiceVehicleCategories(EditorAssetCategory parent)
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Services"
		};
		AddCategory(editorAssetCategory, parent);
		GeneratePublicTransportVehicleCategory(TransportType.Bus, editorAssetCategory);
		GeneratePublicTransportVehicleCategory(TransportType.Taxi, editorAssetCategory);
		GeneratePublicTransportVehicleCategory(TransportType.Tram, editorAssetCategory);
		GeneratePublicTransportVehicleCategory(TransportType.Train, editorAssetCategory);
		GeneratePublicTransportVehicleCategory(TransportType.Subway, editorAssetCategory);
		GeneratePublicTransportVehicleCategory(TransportType.Ship, editorAssetCategory);
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Aircraft",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<AircraftData>(), ComponentType.Exclude<CargoTransportVehicleData>()),
			icon = "Media/Game/Icons/airplane.svg"
		};
		AddCategory(category, editorAssetCategory);
		EditorAssetCategory category2 = new EditorAssetCategory
		{
			id = "Healthcare",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<AmbulanceData>()),
			icon = "Media/Game/Icons/Healthcare.svg"
		};
		AddCategory(category2, editorAssetCategory);
		EditorAssetCategory category3 = new EditorAssetCategory
		{
			id = "Police",
			entityQuery = GetEntityQuery(new EntityQueryDesc
			{
				All = new ComponentType[1] { ComponentType.ReadOnly<VehicleData>() },
				Any = new ComponentType[2]
				{
					ComponentType.ReadOnly<PoliceCarData>(),
					ComponentType.ReadOnly<PublicTransportVehicleData>()
				}
			}),
			icon = "Media/Game/Icons/Police.svg",
			filter = new PublicTransportTypeFilter
			{
				m_TransportType = TransportType.None,
				m_Purpose = PublicTransportPurpose.PrisonerTransport
			}
		};
		AddCategory(category3, editorAssetCategory);
		EditorAssetCategory category4 = new EditorAssetCategory
		{
			id = "Deathcare",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<HearseData>()),
			icon = "Media/Game/Icons/Deathcare.svg"
		};
		AddCategory(category4, editorAssetCategory);
		EditorAssetCategory category5 = new EditorAssetCategory
		{
			id = "FireRescue",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<FireEngineData>()),
			icon = "Media/Game/Icons/FireSafety.svg"
		};
		AddCategory(category5, editorAssetCategory);
		EditorAssetCategory category6 = new EditorAssetCategory
		{
			id = "Garbage",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<GarbageTruckData>()),
			icon = "Media/Game/Icons/Garbage.svg"
		};
		AddCategory(category6, editorAssetCategory);
		EditorAssetCategory category7 = new EditorAssetCategory
		{
			id = "Parks",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<MaintenanceVehicleData>()),
			icon = "Media/Game/Icons/ParksAndRecreation.svg",
			filter = new MaintenanceTypeFilter
			{
				m_Type = MaintenanceType.Park
			}
		};
		AddCategory(category7, editorAssetCategory);
		EditorAssetCategory category8 = new EditorAssetCategory
		{
			id = "Roads",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<MaintenanceVehicleData>()),
			icon = "Media/Game/Icons/Roads.svg",
			filter = new MaintenanceTypeFilter
			{
				m_Type = (MaintenanceType.Road | MaintenanceType.Snow | MaintenanceType.Vehicle)
			}
		};
		AddCategory(category8, editorAssetCategory);
	}
```

- `private GenerateSpawnableBuildingCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateSpawnableBuildingCategories(EditorAssetCategory parent)
	{
		GenerateZoneCategories(AreaType.Residential, office: false, parent);
		GenerateZoneCategories(AreaType.Commercial, office: false, parent);
		GenerateZoneCategories(AreaType.Industrial, office: false, parent);
		GenerateZoneCategories(AreaType.Industrial, office: true, parent);
	}
```

- `private GenerateSurfaceCategories() : System.Void`  

```csharp
private void GenerateSurfaceCategories()
	{
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = "Surfaces",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<SurfaceData>())
		};
		AddCategory(category);
	}
```

- `private GenerateTrackCategories() : System.Void`  

```csharp
private void GenerateTrackCategories()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Tracks",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<TrackData>()),
			includeChildCategories = false
		};
		AddCategory(editorAssetCategory);
		GenerateTrackTypeCategory(TrackTypes.Train, editorAssetCategory);
		GenerateTrackTypeCategory(TrackTypes.Tram, editorAssetCategory);
		GenerateTrackTypeCategory(TrackTypes.Subway, editorAssetCategory);
	}
```

- `private GenerateTrackTypeCategory(Game.Net.TrackTypes trackTypes, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateTrackTypeCategory(TrackTypes trackTypes, EditorAssetCategory parent)
	{
		EditorAssetCategory category = new EditorAssetCategory
		{
			id = trackTypes.ToString(),
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<TrackData>()),
			filter = new TrackTypeFilter
			{
				m_TrackType = trackTypes
			}
		};
		AddCategory(category, parent);
	}
```

- `private GenerateTreeCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateTreeCategories(EditorAssetCategory parent)
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Trees"
		};
		AddCategory(editorAssetCategory, parent);
		foreach (Entity item in m_ThemeQuery.ToEntityArray(Allocator.Temp))
		{
			if (m_PrefabSystem.TryGetPrefab<ThemePrefab>(item, out var prefab))
			{
				string icon = prefab.GetComponent<UIObject>()?.m_Icon;
				EditorAssetCategory category = new EditorAssetCategory
				{
					id = prefab.assetPrefix,
					entityQuery = GetEntityQuery(ComponentType.ReadOnly<TreeData>()),
					icon = icon,
					filter = new ThemeFilter
					{
						m_Theme = item,
						m_DefaultResult = false
					}
				};
				AddCategory(category, editorAssetCategory);
			}
		}
		EditorAssetCategory category2 = new EditorAssetCategory
		{
			id = "Shared",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<TreeData>()),
			filter = new ThemeFilter
			{
				m_Theme = Entity.Null,
				m_DefaultResult = true
			}
		};
		AddCategory(category2, editorAssetCategory);
	}
```

- `private GenerateVehicleCategories() : System.Void`  

```csharp
private void GenerateVehicleCategories()
	{
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = "Vehicles",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<VehicleData>()),
			includeChildCategories = false
		};
		AddCategory(editorAssetCategory);
		GenerateResidentialVehicleCategory(editorAssetCategory);
		GenerateIndustrialVehicleCategory(editorAssetCategory);
		GenerateServiceVehicleCategories(editorAssetCategory);
	}
```

- `private GenerateZoneCategories(Game.Zones.AreaType areaType, System.Boolean office, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private void GenerateZoneCategories(AreaType areaType, bool office, EditorAssetCategory parent)
	{
		string id = (office ? "Office" : areaType.ToString());
		EditorAssetCategory editorAssetCategory = new EditorAssetCategory
		{
			id = id
		};
		AddCategory(editorAssetCategory, parent);
		NativeArray<Entity> nativeArray = m_ZoneQuery.ToEntityArray(Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (m_PrefabSystem.TryGetPrefab<ZonePrefab>(nativeArray[i], out var prefab) && prefab.m_AreaType == areaType && prefab.m_Office == office)
			{
				EditorAssetCategory category = new EditorAssetCategory
				{
					id = prefab.name,
					entityQuery = GetEntityQuery(new EntityQueryDesc
					{
						All = new ComponentType[1] { ComponentType.ReadOnly<BuildingData>() },
						Any = new ComponentType[2]
						{
							ComponentType.ReadOnly<SpawnableBuildingData>(),
							ComponentType.ReadOnly<PlaceholderBuildingData>()
						}
					}),
					filter = new ZoneTypeFilter(nativeArray[i]),
					icon = ImageSystem.GetIcon(prefab)
				};
				AddCategory(category, editorAssetCategory);
			}
		}
		if (areaType == AreaType.Industrial && !office)
		{
			EditorAssetCategory category2 = new EditorAssetCategory
			{
				id = "Extractors",
				entityQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingData>(), ComponentType.ReadOnly<ExtractorFacilityData>())
			};
			AddCategory(category2, editorAssetCategory);
		}
		NativeArray<Entity> nativeArray2 = m_ThemeQuery.ToEntityArray(Allocator.Temp);
		for (int j = 0; j < nativeArray2.Length; j++)
		{
			if (m_PrefabSystem.TryGetPrefab<ThemePrefab>(nativeArray2[j], out var prefab2))
			{
				EditorAssetCategory category3 = new EditorAssetCategory
				{
					id = prefab2.assetPrefix + " Signature",
					entityQuery = GetEntityQuery(ComponentType.ReadOnly<SignatureBuildingData>()),
					filter = new SignatureBuildingFilter
					{
						m_AreaType = areaType,
						m_Office = office,
						m_Theme = nativeArray2[j]
					}
				};
				AddCategory(category3, editorAssetCategory);
			}
		}
		EditorAssetCategory category4 = new EditorAssetCategory
		{
			id = "Signature",
			entityQuery = GetEntityQuery(ComponentType.ReadOnly<SignatureBuildingData>()),
			filter = new SignatureBuildingFilter
			{
				m_AreaType = areaType,
				m_Office = office,
				m_Theme = Entity.Null
			}
		};
		AddCategory(category4, editorAssetCategory);
		nativeArray.Dispose();
	}
```

- `public GetCategories(System.Boolean ignoreEmpty = True) : System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory>`  

```csharp
public IEnumerable<EditorAssetCategory> GetCategories(bool ignoreEmpty = true)
	{
		if (m_Dirty)
		{
			GenerateCategories();
		}
		foreach (var item in GetCategoriesImpl(m_Categories, 0, ignoreEmpty))
		{
			yield return item.Item1;
		}
	}
```

- `private GetCategoriesImpl(System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> categories, System.Int32 level, System.Boolean ignoreEmpty) : System.Collections.Generic.IEnumerable<System.ValueTuple<Game.UI.Editor.EditorAssetCategory, System.Int32>>`  

```csharp
private System.Collections.Generic.IEnumerable<System.ValueTuple<Game.UI.Editor.EditorAssetCategory, System.Int32>> GetCategoriesImpl(System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> categories, System.Int32 level, System.Boolean ignoreEmpty);
```

- `public GetHierarchy(System.Boolean ignoreEmpty = True) : System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>>`  

```csharp
public IEnumerable<HierarchyItem<EditorAssetCategory>> GetHierarchy(bool ignoreEmpty = true)
	{
		if (m_Dirty)
		{
			GenerateCategories();
		}
		foreach (var (editorAssetCategory, level) in GetCategoriesImpl(m_Categories, 0, ignoreEmpty))
		{
			yield return editorAssetCategory.ToHierarchyItem(level);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ServiceQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceData>());
		m_ZoneQuery = GetEntityQuery(ComponentType.ReadOnly<ZoneData>());
		m_ThemeQuery = GetEntityQuery(ComponentType.ReadOnly<ThemeData>());
		m_Overrides = GetEntityQuery(ComponentType.ReadOnly<EditorAssetCategoryOverrideData>());
		m_PrefabModificationQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PrefabData>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
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
		if (!m_PrefabModificationQuery.IsEmptyIgnoreFilter)
		{
			m_Dirty = true;
		}
	}
```


## Nested types

- `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+ServiceTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+ZoneTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+PassengerCountFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+PublicTransportTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+MaintenanceTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+ThemeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+TrackTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+SignatureBuildingFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+TypeHandle`  
- `Game.UI.Editor.EditorAssetCategorySystem+<GetCategories>d__11`  
- `Game.UI.Editor.EditorAssetCategorySystem+<GetCategoriesImpl>d__15`  
- `Game.UI.Editor.EditorAssetCategorySystem+<GetHierarchy>d__12`  
- `Game.UI.Editor.EditorAssetCategorySystem+<__GetCategoriesImpl_17B9CE12>d__51`  

