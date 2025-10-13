# Game.UI.InGame.PoliciesUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliciesUISystem : Game.UI.UISystemBase
{
    public System.Action EventPolicyUnlocked;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.InGame.SelectedInfoUISystem m_InfoSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.EntityQuery m_CityPoliciesQuery;
    private Unity.Entities.EntityQuery m_CityPoliciesUpdatedQuery;
    private Unity.Entities.EntityQuery m_DistrictPoliciesQuery;
    private Unity.Entities.EntityQuery m_BuildingPoliciesQuery;
    private Unity.Entities.EntityQuery m_RoutePoliciesQuery;
    private Unity.Entities.EntityQuery m_PolicyUnlockedQuery;
    private Unity.Entities.EntityArchetype m_PolicyEventArchetype;
    private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_CityPolicies;
    private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_SelectedInfoPolicies;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.InGame.UIPolicy>> m_CityPoliciesBinding;
    private Game.UI.InGame.PoliciesUISystem+TypeHandle __TypeHandle;
    public static const System.String kGroup;

    public PoliciesUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void BindBuildingPolicies(Colossal.UI.Binding.IJsonWriter binder);
    private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> BindCityPolicies();
    public System.Void BindDistrictPolicies(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindPolicies(Colossal.UI.Binding.IJsonWriter binder, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list);
    public System.Void BindRoutePolicies(Colossal.UI.Binding.IJsonWriter binder);
    private Game.UI.InGame.UIPolicy ExtractInfo(Unity.Entities.Entity entity, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.DynamicBuffer<Game.Policies.Policy> activePolicies, System.Boolean slider, Game.Prefabs.PolicySliderData sliderData, System.Int32 priority);
    private System.Boolean FilterPolicy(Unity.Entities.Entity policy, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.Entity target);
    private System.Void FindAndSortPolicies(Unity.Entities.Entity entity, Unity.Entities.EntityQuery policyQuery, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list);
    public System.Boolean GatherSelectedInfoPolicies(Unity.Entities.Entity target);
    private System.Boolean HasParkingLanes(Unity.Entities.Entity building);
    private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects);
    private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets);
    private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes);
    private System.Void ModifyPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RefreshCityPolicyAchievement(Unity.Entities.Entity policy, System.Boolean active);
    public System.Void SetCityPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    public System.Void SetPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    public System.Void SetSelectedInfoPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    public System.Void SetSelectedInfoPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    private System.Void WriteCityPolicies(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> policies);
}
```


## Fields

- `public System.Action EventPolicyUnlocked`  

```csharp
public System.Action EventPolicyUnlocked;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_InfoSystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_InfoSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.EntityQuery m_CityPoliciesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityPoliciesQuery;
```

- `private Unity.Entities.EntityQuery m_CityPoliciesUpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityPoliciesUpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictPoliciesQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictPoliciesQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingPoliciesQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingPoliciesQuery;
```

- `private Unity.Entities.EntityQuery m_RoutePoliciesQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoutePoliciesQuery;
```

- `private Unity.Entities.EntityQuery m_PolicyUnlockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyUnlockedQuery;
```

- `private Unity.Entities.EntityArchetype m_PolicyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PolicyEventArchetype;
```

- `private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_CityPolicies`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_CityPolicies;
```

- `private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_SelectedInfoPolicies`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_SelectedInfoPolicies;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.InGame.UIPolicy>> m_CityPoliciesBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.InGame.UIPolicy>> m_CityPoliciesBinding;
```

- `private Game.UI.InGame.PoliciesUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PoliciesUISystem+TypeHandle __TypeHandle;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Constructors

- `public PoliciesUISystem()`  

```csharp
[Preserve]
	public PoliciesUISystem()
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

- `public BindBuildingPolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
public void BindBuildingPolicies(IJsonWriter binder)
	{
		BindPolicies(binder, m_SelectedInfoPolicies);
	}
```

- `private BindCityPolicies() : System.Collections.Generic.List<Game.UI.InGame.UIPolicy>`  

```csharp
private List<UIPolicy> BindCityPolicies()
	{
		m_CityPolicies.Clear();
		FindAndSortPolicies(m_CitySystem.City, m_CityPoliciesQuery, m_CityPolicies);
		return m_CityPolicies;
	}
```

- `public BindDistrictPolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
public void BindDistrictPolicies(IJsonWriter binder)
	{
		BindPolicies(binder, m_SelectedInfoPolicies);
	}
```

- `private BindPolicies(Colossal.UI.Binding.IJsonWriter binder, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list) : System.Void`  

```csharp
private void BindPolicies(IJsonWriter binder, List<UIPolicy> list)
	{
		binder.ArrayBegin(list.Count);
		for (int i = 0; i < list.Count; i++)
		{
			list[i].Write(m_PrefabUISystem, binder);
		}
		binder.ArrayEnd();
	}
```

- `public BindRoutePolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
public void BindRoutePolicies(IJsonWriter binder)
	{
		BindPolicies(binder, m_SelectedInfoPolicies);
	}
```

- `private ExtractInfo(Unity.Entities.Entity entity, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.DynamicBuffer<Game.Policies.Policy> activePolicies, System.Boolean slider, Game.Prefabs.PolicySliderData sliderData, System.Int32 priority) : Game.UI.InGame.UIPolicy`  

```csharp
private UIPolicy ExtractInfo(Entity entity, PolicyPrefab prefab, DynamicBuffer<Policy> activePolicies, bool slider, PolicySliderData sliderData, int priority)
	{
		string name = prefab.name;
		string icon = ImageSystem.GetIcon(prefab) ?? m_ImageSystem.placeholderIcon;
		bool active = false;
		bool flag = base.EntityManager.HasEnabledComponent<Locked>(entity);
		float value = sliderData.m_Default;
		for (int i = 0; i < activePolicies.Length; i++)
		{
			if (activePolicies[i].m_Policy == entity)
			{
				active = (activePolicies[i].m_Flags & PolicyFlags.Active) != 0;
				value = activePolicies[i].m_Adjustment;
				break;
			}
		}
		if (!GameManager.instance.localizationManager.activeDictionary.TryGetValue($"Policy.TITLE[{name}]", out var value2))
		{
			value2 = string.Empty;
		}
		int milestone = (flag ? ProgressionUtils.GetRequiredMilestone(base.EntityManager, entity) : 0);
		return new UIPolicy(data: new UIPolicySlider(value, sliderData), id: name, localizedName: value2, priority: priority, icon: icon, entity: entity, active: active, locked: flag, uiTag: prefab.uiTag, milestone: milestone, slider: slider);
	}
```

- `private FilterPolicy(Unity.Entities.Entity policy, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.Entity target) : System.Boolean`  

```csharp
private bool FilterPolicy(Entity policy, PolicyPrefab prefab, Entity target)
	{
		if (prefab.m_Visibility == PolicyVisibility.HideFromPolicyList)
		{
			return false;
		}
		if (base.EntityManager.HasComponent<District>(target) || base.EntityManager.HasComponent<Game.City.City>(target) || base.EntityManager.HasComponent<Route>(target))
		{
			return true;
		}
		if (!base.EntityManager.HasComponent<Building>(target))
		{
			return false;
		}
		if (!base.EntityManager.TryGetComponent<BuildingOptionData>(policy, out var component))
		{
			return false;
		}
		if (BuildingUtils.HasOption(component, BuildingOption.PaidParking) && base.EntityManager.TryGetComponent<PrefabRef>(target, out var component2) && base.EntityManager.TryGetComponent<BuildingData>(component2.m_Prefab, out var component3) && (component3.m_Flags & (Game.Prefabs.BuildingFlags.RestrictedPedestrian | Game.Prefabs.BuildingFlags.RestrictedCar)) == 0 && HasParkingLanes(target))
		{
			return true;
		}
		if (BuildingUtils.HasOption(component, BuildingOption.Empty) && base.EntityManager.TryGetComponent<PrefabRef>(target, out var component4) && base.EntityManager.TryGetComponent<GarbageFacilityData>(component4.m_Prefab, out var component5) && component5.m_LongTermStorage)
		{
			return true;
		}
		if (!BuildingUtils.HasOption(component, BuildingOption.Inactive))
		{
			return false;
		}
		if (base.EntityManager.HasComponent<CityServiceUpkeep>(target))
		{
			return base.EntityManager.HasComponent<Efficiency>(target);
		}
		return false;
	}
```

- `private FindAndSortPolicies(Unity.Entities.Entity entity, Unity.Entities.EntityQuery policyQuery, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list) : System.Void`  

```csharp
private void FindAndSortPolicies(Entity entity, EntityQuery policyQuery, List<UIPolicy> list)
	{
		DynamicBuffer<Policy> buffer = base.EntityManager.GetBuffer<Policy>(entity, isReadOnly: true);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PolicySliderData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PolicySliderData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		NativeArray<ArchetypeChunk> nativeArray = policyQuery.ToArchetypeChunkArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			NativeArray<Entity> nativeArray2 = nativeArray[i].GetNativeArray(entityTypeHandle);
			bool flag = nativeArray[i].Has(ref typeHandle);
			NativeArray<PolicySliderData> nativeArray3 = nativeArray[i].GetNativeArray(ref typeHandle);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				PolicyPrefab prefab = m_PrefabSystem.GetPrefab<PolicyPrefab>(nativeArray2[j]);
				int priority = 0;
				if (base.EntityManager.TryGetComponent<UIObjectData>(nativeArray2[j], out var component))
				{
					priority = component.m_Priority;
				}
				if (FilterPolicy(nativeArray2[j], prefab, entity))
				{
					UIPolicy item = ExtractInfo(nativeArray2[j], prefab, buffer, flag, flag ? nativeArray3[j] : default(PolicySliderData), priority);
					list.Add(item);
				}
			}
		}
		list.Sort();
		nativeArray.Dispose();
	}
```

- `public GatherSelectedInfoPolicies(Unity.Entities.Entity target) : System.Boolean`  

```csharp
public bool GatherSelectedInfoPolicies(Entity target)
	{
		m_SelectedInfoPolicies.Clear();
		if (base.EntityManager.HasComponent<Building>(target))
		{
			FindAndSortPolicies(target, m_BuildingPoliciesQuery, m_SelectedInfoPolicies);
		}
		else if (base.EntityManager.HasComponent<District>(target))
		{
			FindAndSortPolicies(target, m_DistrictPoliciesQuery, m_SelectedInfoPolicies);
		}
		else if (base.EntityManager.HasComponent<Route>(target))
		{
			FindAndSortPolicies(target, m_RoutePoliciesQuery, m_SelectedInfoPolicies);
		}
		return m_SelectedInfoPolicies.Count > 0;
	}
```

- `private HasParkingLanes(Unity.Entities.Entity building) : System.Boolean`  

```csharp
private bool HasParkingLanes(DynamicBuffer<Game.Net.SubLane> subLanes)
	{
		for (int i = 0; i < subLanes.Length; i++)
		{
			Entity subLane = subLanes[i].m_SubLane;
			Game.Net.ConnectionLane component2;
			if (base.EntityManager.TryGetComponent<Game.Net.ParkingLane>(subLane, out var component))
			{
				if ((component.m_Flags & ParkingLaneFlags.VirtualLane) == 0)
				{
					return true;
				}
			}
			else if (base.EntityManager.TryGetComponent<Game.Net.ConnectionLane>(subLane, out component2) && (component2.m_Flags & ConnectionLaneFlags.Parking) != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects) : System.Boolean`  

```csharp
private bool HasParkingLanes(DynamicBuffer<Game.Net.SubLane> subLanes)
	{
		for (int i = 0; i < subLanes.Length; i++)
		{
			Entity subLane = subLanes[i].m_SubLane;
			Game.Net.ConnectionLane component2;
			if (base.EntityManager.TryGetComponent<Game.Net.ParkingLane>(subLane, out var component))
			{
				if ((component.m_Flags & ParkingLaneFlags.VirtualLane) == 0)
				{
					return true;
				}
			}
			else if (base.EntityManager.TryGetComponent<Game.Net.ConnectionLane>(subLane, out component2) && (component2.m_Flags & ConnectionLaneFlags.Parking) != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets) : System.Boolean`  

```csharp
private bool HasParkingLanes(DynamicBuffer<Game.Net.SubLane> subLanes)
	{
		for (int i = 0; i < subLanes.Length; i++)
		{
			Entity subLane = subLanes[i].m_SubLane;
			Game.Net.ConnectionLane component2;
			if (base.EntityManager.TryGetComponent<Game.Net.ParkingLane>(subLane, out var component))
			{
				if ((component.m_Flags & ParkingLaneFlags.VirtualLane) == 0)
				{
					return true;
				}
			}
			else if (base.EntityManager.TryGetComponent<Game.Net.ConnectionLane>(subLane, out component2) && (component2.m_Flags & ConnectionLaneFlags.Parking) != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes) : System.Boolean`  

```csharp
private bool HasParkingLanes(DynamicBuffer<Game.Net.SubLane> subLanes)
	{
		for (int i = 0; i < subLanes.Length; i++)
		{
			Entity subLane = subLanes[i].m_SubLane;
			Game.Net.ConnectionLane component2;
			if (base.EntityManager.TryGetComponent<Game.Net.ParkingLane>(subLane, out var component))
			{
				if ((component.m_Flags & ParkingLaneFlags.VirtualLane) == 0)
				{
					return true;
				}
			}
			else if (base.EntityManager.TryGetComponent<Game.Net.ConnectionLane>(subLane, out component2) && (component2.m_Flags & ConnectionLaneFlags.Parking) != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `private ModifyPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment) : System.Void`  

```csharp
private void ModifyPolicy(Entity target, Entity policy, bool active, float adjustment)
	{
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		Entity e = entityCommandBuffer.CreateEntity(m_PolicyEventArchetype);
		entityCommandBuffer.SetComponent(e, new Modify(target, policy, active, adjustment));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_InfoSystem = base.World.GetOrCreateSystemManaged<SelectedInfoUISystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_CityPoliciesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PolicyData>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<CityOptionData>(),
				ComponentType.ReadOnly<CityModifierData>()
			}
		});
		m_CityPoliciesUpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.City.City>(),
				ComponentType.ReadOnly<Policy>(),
				ComponentType.ReadOnly<Updated>()
			}
		});
		m_DistrictPoliciesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PolicyData>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<DistrictOptionData>(),
				ComponentType.ReadOnly<DistrictModifierData>()
			}
		});
		m_BuildingPoliciesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PolicyData>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<BuildingOptionData>(),
				ComponentType.ReadOnly<BuildingModifierData>()
			}
		});
		m_RoutePoliciesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PolicyData>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<RouteOptionData>(),
				ComponentType.ReadOnly<RouteModifierData>()
			}
		});
		m_PolicyUnlockedQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_PolicyEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Modify>());
		m_CityPolicies = new List<UIPolicy>();
		m_SelectedInfoPolicies = new List<UIPolicy>();
		AddBinding(m_CityPoliciesBinding = new GetterValueBinding<List<UIPolicy>>("policies", "cityPolicies", BindCityPolicies, new DelegateWriter<List<UIPolicy>>(WriteCityPolicies)));
		AddBinding(new TriggerBinding<Entity, bool, float>("policies", "setPolicy", SetSelectedInfoPolicy));
		AddBinding(new TriggerBinding<Entity, bool, float>("policies", "setCityPolicy", SetCityPolicy));
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
		base.OnDestroy();
		EventPolicyUnlocked = null;
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_CityPolicies.Clear();
		m_SelectedInfoPolicies.Clear();
		m_CityPoliciesBinding.Update();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (PrefabUtils.HasUnlockedPrefab<PolicyData>(base.EntityManager, m_PolicyUnlockedQuery))
		{
			EventPolicyUnlocked?.Invoke();
			m_CityPoliciesBinding.Update();
		}
		if (!m_CityPoliciesUpdatedQuery.IsEmptyIgnoreFilter)
		{
			m_CityPoliciesBinding.Update();
		}
	}
```

- `private RefreshCityPolicyAchievement(Unity.Entities.Entity policy, System.Boolean active) : System.Void`  

```csharp
private void RefreshCityPolicyAchievement(Entity policy, bool active)
	{
		if (!World.DefaultGameObjectInjectionWorld.EntityManager.TryGetBuffer(m_CitySystem.City, isReadOnly: true, out DynamicBuffer<Policy> buffer))
		{
			return;
		}
		bool flag = false;
		int num = 0;
		for (int i = 0; i < buffer.Length; i++)
		{
			if ((buffer[i].m_Flags & PolicyFlags.Active) != 0)
			{
				num++;
				if (buffer[i].m_Policy == policy)
				{
					flag = true;
				}
			}
		}
		if (active && !flag)
		{
			num++;
		}
		if (!active && flag)
		{
			num--;
		}
		PlatformManager.instance.IndicateAchievementProgress(Game.Achievements.Achievements.CallingtheShots, num);
	}
```

- `public SetCityPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment) : System.Void`  

```csharp
public void SetCityPolicy(Entity policy, bool active, float adjustment)
	{
		ModifyPolicy(m_CitySystem.City, policy, active, adjustment);
		RefreshCityPolicyAchievement(policy, active);
	}
```

- `public SetPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  

```csharp
public void SetPolicy(Entity target, Entity policy, bool active, float adjustment = 0f)
	{
		ModifyPolicy(target, policy, active, adjustment);
	}
```

- `public SetSelectedInfoPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  

```csharp
public void SetSelectedInfoPolicy(Entity target, Entity policy, bool active, float adjustment = 0f)
	{
		ModifyPolicy(target, policy, active, adjustment);
	}
```

- `public SetSelectedInfoPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  

```csharp
public void SetSelectedInfoPolicy(Entity target, Entity policy, bool active, float adjustment = 0f)
	{
		ModifyPolicy(target, policy, active, adjustment);
	}
```

- `private WriteCityPolicies(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> policies) : System.Void`  

```csharp
private void WriteCityPolicies(IJsonWriter writer, List<UIPolicy> policies)
	{
		writer.ArrayBegin(policies.Count);
		foreach (UIPolicy policy in policies)
		{
			policy.Write(m_PrefabUISystem, writer);
		}
		writer.ArrayEnd();
	}
```


## Nested types

- `Game.UI.InGame.PoliciesUISystem+BindingNames`  
- `Game.UI.InGame.PoliciesUISystem+TypeHandle`  

