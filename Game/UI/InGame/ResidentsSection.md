# Game.UI.InGame.ResidentsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResidentsSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Boolean <isHousehold>k__BackingField;
    private System.Int32 <householdCount>k__BackingField;
    private System.Int32 <maxHouseholds>k__BackingField;
    private Game.UI.InGame.HouseholdWealthKey <wealthKey>k__BackingField;
    private System.Int32 <residentCount>k__BackingField;
    private System.Int32 <petCount>k__BackingField;
    private Unity.Entities.Entity <residenceEntity>k__BackingField;
    private Game.UI.InGame.CitizenResidenceKey <residenceKey>k__BackingField;
    private Game.UI.InGame.EducationData <educationData>k__BackingField;
    private Game.UI.InGame.AgeData <ageData>k__BackingField;
    private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Colossal.Collections.NativeValue<Unity.Entities.Entity> m_ResidenceResult;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult;
    private Game.UI.InGame.ResidentsSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private System.Boolean isHousehold { private get; private set; }
    private System.Int32 householdCount { private get; private set; }
    private System.Int32 maxHouseholds { private get; private set; }
    private Game.UI.InGame.HouseholdWealthKey wealthKey { private get; private set; }
    private System.Int32 residentCount { private get; private set; }
    private System.Int32 petCount { private get; private set; }
    private Unity.Entities.Entity residenceEntity { private get; private set; }
    private Game.UI.InGame.CitizenResidenceKey residenceKey { private get; private set; }
    private Game.UI.InGame.EducationData educationData { private get; private set; }
    private Game.UI.InGame.AgeData ageData { private get; private set; }

    public ResidentsSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.AgeData GetAgeData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens);
    private Game.UI.InGame.EducationData GetEducationData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private static System.Boolean TryCountHouseholds(System.Int32& residentCount, System.Int32& petCount, System.Int32& householdCount, System.Int32& maxHouseholds, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkLookup, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandonedLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyDataLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblemLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposeLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdLookup, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizenLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdAnimal, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdAnimalLookup, Unity.Collections.NativeList<Unity.Entities.Entity> householdsResult);
}
```


## Fields

- `private System.Boolean <isHousehold>k__BackingField`  

```csharp
private System.Boolean <isHousehold>k__BackingField;
```

- `private System.Int32 <householdCount>k__BackingField`  

```csharp
private System.Int32 <householdCount>k__BackingField;
```

- `private System.Int32 <maxHouseholds>k__BackingField`  

```csharp
private System.Int32 <maxHouseholds>k__BackingField;
```

- `private Game.UI.InGame.HouseholdWealthKey <wealthKey>k__BackingField`  

```csharp
private Game.UI.InGame.HouseholdWealthKey <wealthKey>k__BackingField;
```

- `private System.Int32 <residentCount>k__BackingField`  

```csharp
private System.Int32 <residentCount>k__BackingField;
```

- `private System.Int32 <petCount>k__BackingField`  

```csharp
private System.Int32 <petCount>k__BackingField;
```

- `private Unity.Entities.Entity <residenceEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <residenceEntity>k__BackingField;
```

- `private Game.UI.InGame.CitizenResidenceKey <residenceKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenResidenceKey <residenceKey>k__BackingField;
```

- `private Game.UI.InGame.EducationData <educationData>k__BackingField`  

```csharp
private Game.UI.InGame.EducationData <educationData>k__BackingField;
```

- `private Game.UI.InGame.AgeData <ageData>k__BackingField`  

```csharp
private Game.UI.InGame.AgeData <ageData>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Colossal.Collections.NativeValue<Unity.Entities.Entity> m_ResidenceResult`  

```csharp
private Colossal.Collections.NativeValue<Unity.Entities.Entity> m_ResidenceResult;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult;
```

- `private Game.UI.InGame.ResidentsSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.ResidentsSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Boolean isHousehold { private get; private set }`  

```csharp
private System.Boolean isHousehold { private get; private set; }
```

- `private System.Int32 householdCount { private get; private set }`  

```csharp
private System.Int32 householdCount { private get; private set; }
```

- `private System.Int32 maxHouseholds { private get; private set }`  

```csharp
private System.Int32 maxHouseholds { private get; private set; }
```

- `private Game.UI.InGame.HouseholdWealthKey wealthKey { private get; private set }`  

```csharp
private Game.UI.InGame.HouseholdWealthKey wealthKey { private get; private set; }
```

- `private System.Int32 residentCount { private get; private set }`  

```csharp
private System.Int32 residentCount { private get; private set; }
```

- `private System.Int32 petCount { private get; private set }`  

```csharp
private System.Int32 petCount { private get; private set; }
```

- `private Unity.Entities.Entity residenceEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity residenceEntity { private get; private set; }
```

- `private Game.UI.InGame.CitizenResidenceKey residenceKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenResidenceKey residenceKey { private get; private set; }
```

- `private Game.UI.InGame.EducationData educationData { private get; private set }`  

```csharp
private Game.UI.InGame.EducationData educationData { private get; private set; }
```

- `private Game.UI.InGame.AgeData ageData { private get; private set }`  

```csharp
private Game.UI.InGame.AgeData ageData { private get; private set; }
```


## Constructors

- `public ResidentsSection()`  

```csharp
[Preserve]
	public ResidentsSection()
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

- `private GetAgeData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens) : Game.UI.InGame.AgeData`  

```csharp
private AgeData GetAgeData(DynamicBuffer<HouseholdCitizen> citizens)
	{
		int num = 0;
		int num2 = 0;
		int num3 = 0;
		int num4 = 0;
		for (int i = 0; i < citizens.Length; i++)
		{
			Entity citizen = citizens[i].m_Citizen;
			if (base.EntityManager.TryGetComponent<Citizen>(citizen, out var component) && !CitizenUtils.IsCorpsePickedByHearse(base.EntityManager, citizen))
			{
				switch (component.GetAge())
				{
				case CitizenAge.Child:
					num++;
					break;
				case CitizenAge.Teen:
					num2++;
					break;
				case CitizenAge.Adult:
					num3++;
					break;
				case CitizenAge.Elderly:
					num4++;
					break;
				}
			}
		}
		return new AgeData(num, num2, num3, num4);
	}
```

- `private GetEducationData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens) : Game.UI.InGame.EducationData`  

```csharp
private EducationData GetEducationData(DynamicBuffer<HouseholdCitizen> citizens)
	{
		int num = 0;
		int num2 = 0;
		int num3 = 0;
		int num4 = 0;
		int num5 = 0;
		for (int i = 0; i < citizens.Length; i++)
		{
			if (base.EntityManager.TryGetComponent<Citizen>(citizens[i].m_Citizen, out var component) && !CitizenUtils.IsCorpsePickedByHearse(base.EntityManager, citizens[i].m_Citizen))
			{
				switch (component.GetEducationLevel())
				{
				case 0:
					num++;
					break;
				case 1:
					num2++;
					break;
				case 2:
					num3++;
					break;
				case 3:
					num4++;
					break;
				case 4:
					num5++;
					break;
				}
			}
		}
		return new EducationData(num, num2, num3, num4, num5);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_DistrictBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<ResidentialProperty>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Renter>(), ComponentType.ReadOnly<CurrentDistrict>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_HappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		m_HouseholdsResult = new NativeList<Entity>(Allocator.Persistent);
		m_ResidenceResult = new NativeValue<Entity>(Allocator.Persistent);
		m_Results = new NativeArray<int>(5, Allocator.Persistent);
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
		m_HouseholdsResult.Dispose();
		m_ResidenceResult.Dispose();
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (base.EntityManager.HasComponent<Household>(selectedEntity))
		{
			isHousehold = true;
		}
		householdCount = m_Results[3];
		residentCount = m_Results[1];
		petCount = m_Results[2];
		maxHouseholds = m_Results[4];
		wealthKey = CitizenUIUtils.GetAverageHouseholdWealth(base.EntityManager, m_HouseholdsResult, m_HappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>());
		DynamicBuffer<HouseholdCitizen> buffer2;
		if (!isHousehold)
		{
			for (int i = 0; i < m_HouseholdsResult.Length; i++)
			{
				DynamicBuffer<HouseholdCitizen> buffer = base.EntityManager.GetBuffer<HouseholdCitizen>(m_HouseholdsResult[i], isReadOnly: true);
				ageData += GetAgeData(buffer);
				educationData += GetEducationData(buffer);
			}
		}
		else if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out buffer2))
		{
			ageData += GetAgeData(buffer2);
			educationData += GetEducationData(buffer2);
		}
		if (!base.EntityManager.Exists(m_ResidenceResult.value))
		{
			residenceEntity = Entity.Null;
			residenceKey = CitizenResidenceKey.Home;
			return;
		}
		residenceEntity = m_ResidenceResult.value;
		residenceKey = (base.EntityManager.HasComponent<TouristHousehold>(selectedEntity) ? CitizenResidenceKey.Hotel : (base.EntityManager.HasComponent<HomelessHousehold>(selectedEntity) ? CitizenResidenceKey.Shelter : CitizenResidenceKey.Home));
		DynamicBuffer<Renter> buffer4;
		if ((base.EntityManager.HasComponent<Game.Buildings.Park>(residenceEntity) || base.EntityManager.HasComponent<Abandoned>(residenceEntity)) && base.EntityManager.TryGetBuffer(residenceEntity, isReadOnly: true, out DynamicBuffer<Renter> buffer3) && buffer3.Length > 0)
		{
			m_InfoUISystem.tooltipTags.Add(TooltipTags.HomelessShelter);
			base.tooltipTags.Add(TooltipTags.HomelessShelter.ToString());
			base.tooltipKeys.Add(TooltipTags.HomelessShelter.ToString());
		}
		else if ((base.EntityManager.HasComponent<Game.Buildings.Park>(selectedEntity) || base.EntityManager.HasComponent<Abandoned>(selectedEntity)) && base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out buffer4) && buffer4.Length > 0)
		{
			m_InfoUISystem.tooltipTags.Add(TooltipTags.HomelessShelter);
			base.tooltipTags.Add(TooltipTags.HomelessShelter.ToString());
			base.tooltipKeys.Add(TooltipTags.HomelessShelter.ToString());
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (base.EntityManager.HasComponent<District>(selectedEntity) && base.EntityManager.HasComponent<Area>(selectedEntity))
		{
			JobChunkExtensions.Schedule(new CountDistrictHouseholdsJob
			{
				m_SelectedEntity = selectedEntity,
				m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CurrentDistrictHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ParkLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AbandonedLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HealthProblemLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TravelPurposeLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyDataLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizenLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_HouseholdAnimalLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdAnimal_RO_BufferLookup, ref base.CheckedStateRef),
				m_RenterLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_Results = m_Results,
				m_HouseholdsResult = m_HouseholdsResult
			}, m_DistrictBuildingQuery, base.Dependency).Complete();
			base.visible = m_Results[0] > 0;
		}
		else
		{
			IJobExtensions.Schedule(new CountHouseholdsJob
			{
				m_SelectedEntity = selectedEntity,
				m_SelectedPrefab = selectedPrefab,
				m_BuildingLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ParkLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AbandonedLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HomelessHouseholdLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HealthProblemLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TravelPurposeLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenterLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyDataLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizenLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_HouseholdAnimalLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdAnimal_RO_BufferLookup, ref base.CheckedStateRef),
				m_RenterLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_Results = m_Results,
				m_HouseholdsResult = m_HouseholdsResult,
				m_ResidenceResult = m_ResidenceResult
			}, base.Dependency).Complete();
			base.visible = m_Results[0] > 0;
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("isHousehold");
		writer.Write(isHousehold);
		writer.PropertyName("householdCount");
		writer.Write(householdCount);
		writer.PropertyName("maxHouseholds");
		writer.Write(maxHouseholds);
		writer.PropertyName("residentCount");
		writer.Write(residentCount);
		writer.PropertyName("petCount");
		writer.Write(petCount);
		writer.PropertyName("wealthKey");
		writer.Write(wealthKey.ToString());
		writer.PropertyName("residence");
		if (residenceEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, residenceEntity);
		}
		writer.PropertyName("residenceEntity");
		if (residenceEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(residenceEntity);
		}
		writer.PropertyName("residenceKey");
		writer.Write(Enum.GetName(typeof(CitizenResidenceKey), residenceKey));
		writer.PropertyName("ageData");
		writer.Write(ageData);
		writer.PropertyName("educationData");
		writer.Write(educationData);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		isHousehold = false;
		householdCount = 0;
		maxHouseholds = 0;
		residentCount = 0;
		petCount = 0;
		educationData = default(EducationData);
		ageData = default(AgeData);
		m_HouseholdsResult.Clear();
		m_ResidenceResult.value = Entity.Null;
		m_Results[0] = 0;
		m_Results[1] = 0;
		m_Results[2] = 0;
		m_Results[4] = 0;
		m_Results[3] = 0;
	}
```

- `private static TryCountHouseholds(System.Int32& residentCount, System.Int32& petCount, System.Int32& householdCount, System.Int32& maxHouseholds, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkLookup, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandonedLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyDataLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblemLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposeLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdLookup, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizenLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdAnimal, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdAnimalLookup, Unity.Collections.NativeList<Unity.Entities.Entity> householdsResult) : System.Boolean`  

```csharp
private static bool TryCountHouseholds(ref int residentCount, ref int petCount, ref int householdCount, ref int maxHouseholds, Entity entity, Entity prefab, ref ComponentLookup<Game.Buildings.Park> parkLookup, ref ComponentLookup<Abandoned> abandonedLookup, ref ComponentLookup<BuildingPropertyData> propertyDataLookup, ref ComponentLookup<HealthProblem> healthProblemLookup, ref ComponentLookup<TravelPurpose> travelPurposeLookup, ref ComponentLookup<Household> householdLookup, ref BufferLookup<Renter> renterLookup, ref BufferLookup<HouseholdCitizen> householdCitizenLookup, ref BufferLookup<HouseholdAnimal> householdAnimalLookup, NativeList<Entity> householdsResult)
	{
		bool result = false;
		bool flag = abandonedLookup.HasComponent(entity);
		DynamicBuffer<Renter> bufferData;
		bool flag2 = renterLookup.TryGetBuffer(entity, out bufferData) && bufferData.Length > 0;
		bool flag3 = parkLookup.HasComponent(entity);
		BuildingPropertyData componentData;
		bool num = propertyDataLookup.TryGetComponent(prefab, out componentData) && componentData.m_ResidentialProperties > 0 && !flag;
		bool flag4 = (flag3 || flag) && flag2;
		if (num || flag4)
		{
			result = true;
			maxHouseholds += componentData.m_ResidentialProperties;
			for (int i = 0; i < bufferData.Length; i++)
			{
				Entity value = bufferData[i].m_Renter;
				if (!householdLookup.HasComponent(value) || !householdCitizenLookup.TryGetBuffer(value, out var bufferData2))
				{
					continue;
				}
				householdCount++;
				householdsResult.Add(in value);
				for (int j = 0; j < bufferData2.Length; j++)
				{
					if (!CitizenUtils.IsCorpsePickedByHearse(bufferData2[j].m_Citizen, ref healthProblemLookup, ref travelPurposeLookup))
					{
						residentCount++;
					}
				}
				if (householdAnimalLookup.TryGetBuffer(value, out var bufferData3))
				{
					petCount += bufferData3.Length;
				}
			}
		}
		return result;
	}
```


## Nested types

- `Game.UI.InGame.ResidentsSection+Result`  
- `Game.UI.InGame.ResidentsSection+CountHouseholdsJob`  
- `Game.UI.InGame.ResidentsSection+CountDistrictHouseholdsJob`  
- `Game.UI.InGame.ResidentsSection+TypeHandle`  

