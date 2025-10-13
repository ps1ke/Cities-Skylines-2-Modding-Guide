# Game.UI.InGame.HouseholdSidebarSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdSidebarSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <residenceEntity>k__BackingField;
    private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult <household>k__BackingField;
    private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant <variant>k__BackingField;
    private System.Boolean <residenceIsHomelessShelter>k__BackingField;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResidenceResult;
    private Unity.Collections.NativeArray<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdResult;
    private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+ResidentResult> m_ResidentsResult;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_PetsResult;
    private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdsResult;
    private Colossal.UI.Binding.RawMapBinding<System.Int32> m_HouseholdMap;
    private Colossal.UI.Binding.RawMapBinding<System.Int32> m_ResidentMap;
    private Colossal.UI.Binding.RawMapBinding<System.Int32> m_PetMap;
    private Game.UI.InGame.HouseholdSidebarSection+TypeHandle __TypeHandle;
    private static const System.String kHouseholdIcon;
    private static const System.String kResidenceIcon;
    private static const System.String kHomelessShelterIcon;
    private static const System.String kPetIcon;
    private static const System.String kItemType;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    private Unity.Entities.Entity residenceEntity { private get; private set; }
    private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult household { private get; private set; }
    private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant variant { private get; private set; }
    private System.Boolean residenceIsHomelessShelter { private get; private set; }

    public HouseholdSidebarSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void BindHousehold(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
    private System.Void BindPet(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
    private System.Void BindResident(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Void WriteItem(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.String iconPath, System.Int32 memberCount);
}
```


## Fields

- `private Unity.Entities.Entity <residenceEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <residenceEntity>k__BackingField;
```

- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult <household>k__BackingField`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult <household>k__BackingField;
```

- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant <variant>k__BackingField`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant <variant>k__BackingField;
```

- `private System.Boolean <residenceIsHomelessShelter>k__BackingField`  

```csharp
private System.Boolean <residenceIsHomelessShelter>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResidenceResult`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResidenceResult;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdResult`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+ResidentResult> m_ResidentsResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+ResidentResult> m_ResidentsResult;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_PetsResult`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_PetsResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdsResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult> m_HouseholdsResult;
```

- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_HouseholdMap`  

```csharp
private Colossal.UI.Binding.RawMapBinding<System.Int32> m_HouseholdMap;
```

- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_ResidentMap`  

```csharp
private Colossal.UI.Binding.RawMapBinding<System.Int32> m_ResidentMap;
```

- `private Colossal.UI.Binding.RawMapBinding<System.Int32> m_PetMap`  

```csharp
private Colossal.UI.Binding.RawMapBinding<System.Int32> m_PetMap;
```

- `private Game.UI.InGame.HouseholdSidebarSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+TypeHandle __TypeHandle;
```

- `private static const System.String kHouseholdIcon`  

```csharp
private static const System.String kHouseholdIcon;
```

- `private static const System.String kResidenceIcon`  

```csharp
private static const System.String kResidenceIcon;
```

- `private static const System.String kHomelessShelterIcon`  

```csharp
private static const System.String kHomelessShelterIcon;
```

- `private static const System.String kPetIcon`  

```csharp
private static const System.String kPetIcon;
```

- `private static const System.String kItemType`  

```csharp
private static const System.String kItemType;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `private Unity.Entities.Entity residenceEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity residenceEntity { private get; private set; }
```

- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult household { private get; private set }`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+HouseholdResult household { private get; private set; }
```

- `private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant variant { private get; private set }`  

```csharp
private Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant variant { private get; private set; }
```

- `private System.Boolean residenceIsHomelessShelter { private get; private set }`  

```csharp
private System.Boolean residenceIsHomelessShelter { private get; private set; }
```


## Constructors

- `public HouseholdSidebarSection()`  

```csharp
[Preserve]
	public HouseholdSidebarSection()
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

- `private BindHousehold(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  

```csharp
private void BindHousehold(IJsonWriter writer, int index)
	{
		Entity entity = m_HouseholdsResult[index].m_Entity;
		WriteItem(writer, entity, "Media/Game/Icons/Household.svg", base.EntityManager.GetBuffer<HouseholdCitizen>(entity).Length);
	}
```

- `private BindPet(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  

```csharp
private void BindPet(IJsonWriter writer, int index)
	{
		Entity entity = m_PetsResult[index];
		WriteItem(writer, entity, "Media/Game/Icons/Pet.svg");
	}
```

- `private BindResident(Colossal.UI.Binding.IJsonWriter writer, System.Int32 index) : System.Void`  

```csharp
private void BindResident(IJsonWriter writer, int index)
	{
		Entity entity = m_ResidentsResult[index].m_Entity;
		WriteItem(writer, entity, null);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResidentsResult = new NativeList<ResidentResult>(Allocator.Persistent);
		m_PetsResult = new NativeList<Entity>(Allocator.Persistent);
		m_HouseholdsResult = new NativeList<HouseholdResult>(Allocator.Persistent);
		m_Results = new NativeArray<int>(3, Allocator.Persistent);
		m_ResidenceResult = new NativeArray<Entity>(1, Allocator.Persistent);
		m_HouseholdResult = new NativeArray<HouseholdResult>(1, Allocator.Persistent);
		AddBinding(m_HouseholdMap = new RawMapBinding<int>(group, "householdMap", BindHousehold));
		AddBinding(m_ResidentMap = new RawMapBinding<int>(group, "residentMap", BindResident));
		AddBinding(m_PetMap = new RawMapBinding<int>(group, "petMap", BindPet));
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
		m_ResidentsResult.Dispose();
		m_HouseholdResult.Dispose();
		m_PetsResult.Dispose();
		m_HouseholdsResult.Dispose();
		m_Results.Dispose();
		m_ResidenceResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		residenceEntity = m_ResidenceResult[0];
		household = m_HouseholdResult[0];
		variant = (HouseholdSidebarVariant)m_Results[2];
		if (!base.EntityManager.Exists(residenceEntity))
		{
			residenceEntity = Entity.Null;
		}
		if ((base.EntityManager.HasComponent<Game.Buildings.Park>(residenceEntity) || base.EntityManager.HasComponent<Abandoned>(residenceEntity)) && base.EntityManager.TryGetBuffer(residenceEntity, isReadOnly: true, out DynamicBuffer<Renter> buffer) && buffer.Length > 0)
		{
			m_InfoUISystem.tooltipTags.Add(TooltipTags.HomelessShelter);
			base.tooltipTags.Add(TooltipTags.HomelessShelter.ToString());
			base.tooltipKeys.Add(TooltipTags.HomelessShelter.ToString());
			residenceIsHomelessShelter = true;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		IJobExtensions.Schedule(new CheckVisibilityJob
		{
			m_SelectedEntity = selectedEntity,
			m_SelectedPrefab = selectedPrefab,
			m_ParkFromLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AbandonedLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CitizenLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdPetLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdPet_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblemLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TravelPurposeLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyDataLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizenLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_RenterLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, base.Dependency).Complete();
		base.visible = m_Results[0] == 1 && m_Results[1] > 0;
		if (base.visible)
		{
			IJobExtensions.Schedule(new CollectDataJob
			{
				m_SelectedEntity = selectedEntity,
				m_BuildingLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HomelessHouseholdLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CitizenLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdMemberLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdPetLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdPet_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HealthProblemLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TravelPurposeLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenterLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizenLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_ResourcesLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
				m_HouseholdAnimalsLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdAnimal_RO_BufferLookup, ref base.CheckedStateRef),
				m_RenterLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_ResidenceResult = m_ResidenceResult,
				m_HouseholdResult = m_HouseholdResult,
				m_HouseholdsResult = m_HouseholdsResult,
				m_ResidentsResult = m_ResidentsResult,
				m_PetsResult = m_PetsResult
			}, base.Dependency).Complete();
			m_HouseholdsResult.Sort();
			m_ResidentsResult.Sort();
			m_PetsResult.Sort();
			for (int i = 0; i < m_HouseholdsResult.Length; i++)
			{
				m_HouseholdMap.Update(i);
			}
			for (int j = 0; j < m_ResidentsResult.Length; j++)
			{
				m_ResidentMap.Update(j);
			}
			for (int k = 0; k < m_PetsResult.Length; k++)
			{
				m_PetMap.Update(k);
			}
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("variant");
		writer.Write(variant.ToString());
		writer.PropertyName("residence");
		WriteItem(writer, residenceEntity, residenceIsHomelessShelter ? "Media/Glyphs/HomelessShelter.svg" : "Media/Glyphs/Residence.svg");
		writer.PropertyName("household");
		WriteItem(writer, household.m_Entity, "Media/Game/Icons/Household.svg", household.m_Members);
		writer.PropertyName("households");
		writer.Write(m_HouseholdsResult.Length);
		writer.PropertyName("residents");
		writer.Write(m_ResidentsResult.Length);
		writer.PropertyName("pets");
		writer.Write(m_PetsResult.Length);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		m_ResidentsResult.Clear();
		m_PetsResult.Clear();
		m_HouseholdsResult.Clear();
		m_ResidenceResult[0] = Entity.Null;
		m_HouseholdResult[0] = default(HouseholdResult);
		m_Results[0] = 0;
		m_Results[1] = 0;
		m_Results[2] = 0;
		residenceIsHomelessShelter = false;
	}
```

- `private WriteItem(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.String iconPath, System.Int32 memberCount = 0) : System.Void`  

```csharp
private void WriteItem(IJsonWriter writer, Entity entity, string iconPath, int memberCount = 0)
	{
		writer.TypeBegin("Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarItem");
		writer.PropertyName("entity");
		writer.Write(entity);
		writer.PropertyName("name");
		m_NameSystem.BindName(writer, entity);
		writer.PropertyName("familyName");
		if (entity == Entity.Null || !base.EntityManager.HasComponent<Household>(entity))
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindFamilyName(writer, entity);
		}
		writer.PropertyName("icon");
		writer.Write(iconPath);
		writer.PropertyName("selected");
		writer.Write(entity == selectedEntity);
		writer.PropertyName("count");
		if (memberCount == 0)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(memberCount);
		}
		writer.TypeEnd();
	}
```


## Nested types

- `Game.UI.InGame.HouseholdSidebarSection+Result`  
- `Game.UI.InGame.HouseholdSidebarSection+HouseholdSidebarVariant`  
- `Game.UI.InGame.HouseholdSidebarSection+CheckVisibilityJob`  
- `Game.UI.InGame.HouseholdSidebarSection+CollectDataJob`  
- `Game.UI.InGame.HouseholdSidebarSection+HouseholdResult`  
- `Game.UI.InGame.HouseholdSidebarSection+HouseholdComparer`  
- `Game.UI.InGame.HouseholdSidebarSection+ResidentResult`  
- `Game.UI.InGame.HouseholdSidebarSection+ResidentComparer`  
- `Game.UI.InGame.HouseholdSidebarSection+TypeHandle`  

