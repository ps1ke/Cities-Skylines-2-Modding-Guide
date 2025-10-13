# Game.UI.InGame.LifePathUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LifePathUISystem : Game.UI.UISystemBase
{
    private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.UI.InGame.ChirperUISystem m_ChirperUISystem;
    private Unity.Entities.EntityQuery m_FollowedQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private System.Int32 m_FollowedVersion;
    private System.Int32 m_LifePathEntryVersion;
    private System.Int32 m_ChirpVersion;
    private Colossal.UI.Binding.RawValueBinding m_FollowedCitizensBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathDetailsBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathItemsBinding;
    private static const System.String kGroup;

    public LifePathUISystem();

    private System.Void <OnCreate>b__13_0(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
    private System.Void <OnCreate>b__13_1(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
    private System.Void BindFollowedCitizens(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindLifePathDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.Void BindLifePathEvent(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.Void BindLifePathItems(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
    private System.Void FollowCitizen(Unity.Entities.Entity citizen);
    private System.Int32 GetRandomIndex(Unity.Entities.Entity entity);
    private Unity.Collections.NativeArray<Unity.Entities.Entity> GetSortedFollowedCitizens();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void UnfollowCitizen(Unity.Entities.Entity citizen);
}
```


## Fields

- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  

```csharp
private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.UI.InGame.ChirperUISystem m_ChirperUISystem`  

```csharp
private Game.UI.InGame.ChirperUISystem m_ChirperUISystem;
```

- `private Unity.Entities.EntityQuery m_FollowedQuery`  

```csharp
private Unity.Entities.EntityQuery m_FollowedQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private System.Int32 m_FollowedVersion`  

```csharp
private System.Int32 m_FollowedVersion;
```

- `private System.Int32 m_LifePathEntryVersion`  

```csharp
private System.Int32 m_LifePathEntryVersion;
```

- `private System.Int32 m_ChirpVersion`  

```csharp
private System.Int32 m_ChirpVersion;
```

- `private Colossal.UI.Binding.RawValueBinding m_FollowedCitizensBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_FollowedCitizensBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathDetailsBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathItemsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathItemsBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public LifePathUISystem()`  

```csharp
[Preserve]
	public LifePathUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__13_0(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  

```csharp
private System.Void <OnCreate>b__13_0(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
```

- `private <OnCreate>b__13_1(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  

```csharp
private System.Void <OnCreate>b__13_1(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
```

- `private BindFollowedCitizens(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindFollowedCitizens(IJsonWriter binder)
	{
		NativeArray<Entity> sortedFollowedCitizens = GetSortedFollowedCitizens();
		binder.ArrayBegin(sortedFollowedCitizens.Length);
		for (int i = 0; i < sortedFollowedCitizens.Length; i++)
		{
			Entity entity = sortedFollowedCitizens[i];
			binder.TypeBegin("lifePath.FollowedCitizen");
			binder.PropertyName("entity");
			binder.Write(entity);
			binder.PropertyName("name");
			m_NameSystem.BindName(binder, entity);
			binder.PropertyName("age");
			binder.Write(Enum.GetName(typeof(CitizenAgeKey), CitizenUIUtils.GetAge(base.EntityManager, entity)));
			binder.PropertyName("dead");
			binder.Write(CitizenUtils.IsDead(base.EntityManager, entity));
			binder.TypeEnd();
		}
		binder.ArrayEnd();
		sortedFollowedCitizens.Dispose();
	}
```

- `private BindLifePathDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void BindLifePathDetails(IJsonWriter binder, Entity entity)
	{
		if (base.EntityManager.TryGetComponent<Citizen>(entity, out var component) && base.EntityManager.HasComponent<Followed>(entity))
		{
			Entity residenceEntity = CitizenUIUtils.GetResidenceEntity(base.EntityManager, entity);
			CitizenResidenceKey residenceType = CitizenUIUtils.GetResidenceType(base.EntityManager, entity);
			Entity workplaceEntity = CitizenUIUtils.GetWorkplaceEntity(base.EntityManager, entity);
			Entity companyEntity = CitizenUIUtils.GetCompanyEntity(base.EntityManager, entity);
			CitizenWorkplaceKey workplaceType = CitizenUIUtils.GetWorkplaceType(base.EntityManager, entity);
			int level;
			Entity schoolEntity = CitizenUIUtils.GetSchoolEntity(base.EntityManager, entity, out level);
			CitizenOccupationKey occupation = CitizenUIUtils.GetOccupation(base.EntityManager, entity);
			CitizenJobLevelKey jobLevel = CitizenUIUtils.GetJobLevel(base.EntityManager, entity);
			CitizenAgeKey age = CitizenUIUtils.GetAge(base.EntityManager, entity);
			CitizenEducationKey education = CitizenUIUtils.GetEducation(component);
			HouseholdMember componentData = base.EntityManager.GetComponentData<HouseholdMember>(entity);
			NativeList<CitizenCondition> citizenConditions = CitizenUIUtils.GetCitizenConditions(base.EntityManager, entity, component, componentData, new NativeList<CitizenCondition>(Allocator.TempJob));
			HouseholdWealthKey householdWealth = CitizenUIUtils.GetHouseholdWealth(base.EntityManager, componentData.m_Household, m_HappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>());
			bool flag = CitizenUtils.IsDead(base.EntityManager, entity);
			binder.TypeBegin("lifePath.LifePathDetails");
			binder.PropertyName("entity");
			binder.Write(entity);
			binder.PropertyName("name");
			m_NameSystem.BindName(binder, entity);
			binder.PropertyName("avatar");
			binder.WriteNull();
			binder.PropertyName("randomIndex");
			binder.Write(GetRandomIndex(entity));
			binder.PropertyName("birthDay");
			binder.Write(component.m_BirthDay);
			binder.PropertyName("age");
			binder.Write(Enum.GetName(typeof(CitizenAgeKey), age));
			binder.PropertyName("education");
			binder.Write(Enum.GetName(typeof(CitizenEducationKey), education));
			binder.PropertyName("wealth");
			binder.Write(Enum.GetName(typeof(HouseholdWealthKey), householdWealth));
			binder.PropertyName("occupation");
			binder.Write(Enum.GetName(typeof(CitizenOccupationKey), occupation));
			binder.PropertyName("jobLevel");
			binder.Write(Enum.GetName(typeof(CitizenJobLevelKey), jobLevel));
			binder.PropertyName("residenceName");
			if (residenceEntity == Entity.Null)
			{
				binder.WriteNull();
			}
			else
			{
				m_NameSystem.BindName(binder, residenceEntity);
			}
			binder.PropertyName("residenceEntity");
			if (residenceEntity == Entity.Null)
			{
				binder.WriteNull();
			}
			else
			{
				binder.Write(residenceEntity);
			}
			binder.PropertyName("residenceKey");
			binder.Write(Enum.GetName(typeof(CitizenResidenceKey), residenceType));
			binder.PropertyName("workplaceName");
			if (companyEntity == Entity.Null)
			{
				binder.WriteNull();
			}
			else
			{
				m_NameSystem.BindName(binder, companyEntity);
			}
			binder.PropertyName("workplaceEntity");
			if (workplaceEntity == Entity.Null)
			{
				binder.WriteNull();
			}
			else
			{
				binder.Write(workplaceEntity);
			}
			binder.PropertyName("workplaceKey");
			binder.Write(Enum.GetName(typeof(CitizenWorkplaceKey), workplaceType));
			binder.PropertyName("schoolName");
			if (schoolEntity == Entity.Null)
			{
				binder.WriteNull();
			}
			else
			{
				m_NameSystem.BindName(binder, schoolEntity);
			}
			binder.PropertyName("schoolEntity");
			if (schoolEntity == Entity.Null)
			{
				binder.WriteNull();
			}
			else
			{
				binder.Write(schoolEntity);
			}
			binder.PropertyName("conditions");
			if (flag)
			{
				binder.WriteEmptyArray();
			}
			else
			{
				binder.ArrayBegin(citizenConditions.Length);
				for (int i = 0; i < citizenConditions.Length; i++)
				{
					binder.Write(citizenConditions[i]);
				}
				binder.ArrayEnd();
			}
			binder.PropertyName("happiness");
			if (flag)
			{
				binder.WriteNull();
			}
			else
			{
				binder.Write(CitizenUIUtils.GetCitizenHappiness(component));
			}
			binder.PropertyName("state");
			binder.Write(Enum.GetName(typeof(CitizenStateKey), CitizenUIUtils.GetStateKey(base.EntityManager, entity)));
			binder.TypeEnd();
			citizenConditions.Dispose();
		}
		else
		{
			binder.WriteNull();
		}
	}
```

- `private BindLifePathEvent(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void BindLifePathEvent(IJsonWriter binder, Entity entity)
	{
		string messageID = m_ChirperUISystem.GetMessageID(entity);
		Game.Triggers.LifePathEvent componentData = base.EntityManager.GetComponentData<Game.Triggers.LifePathEvent>(entity);
		binder.TypeBegin("lifePath.LifePathEvent");
		binder.PropertyName("entity");
		binder.Write(entity);
		binder.PropertyName("date");
		binder.Write(componentData.m_Date);
		binder.PropertyName("messageId");
		binder.Write(messageID);
		binder.TypeEnd();
	}
```

- `private BindLifePathItems(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  

```csharp
private void BindLifePathItems(IJsonWriter binder, Entity citizen)
	{
		if (base.EntityManager.TryGetBuffer(citizen, isReadOnly: true, out DynamicBuffer<LifePathEntry> buffer))
		{
			binder.ArrayBegin(buffer.Length);
			for (int num = buffer.Length - 1; num >= 0; num--)
			{
				Entity entity = buffer[num].m_Entity;
				if (!base.EntityManager.HasComponent<Deleted>(entity))
				{
					if (base.EntityManager.HasComponent<Game.Triggers.Chirp>(entity))
					{
						m_ChirperUISystem.BindChirp(binder, entity);
					}
					else if (base.EntityManager.HasComponent<Game.Triggers.LifePathEvent>(entity))
					{
						BindLifePathEvent(binder, entity);
					}
					else
					{
						binder.WriteNull();
					}
				}
				else
				{
					binder.WriteNull();
				}
			}
			binder.ArrayEnd();
		}
		else
		{
			binder.WriteEmptyArray();
		}
	}
```

- `private FollowCitizen(Unity.Entities.Entity citizen) : System.Void`  

```csharp
private void FollowCitizen(Entity citizen)
	{
		m_LifePathEventSystem.FollowCitizen(citizen);
	}
```

- `private GetRandomIndex(Unity.Entities.Entity entity) : System.Int32`  

```csharp
private int GetRandomIndex(Entity entity)
	{
		if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<RandomLocalizationIndex> buffer) && buffer.Length > 0)
		{
			return buffer[0].m_Index;
		}
		return 0;
	}
```

- `private GetSortedFollowedCitizens() : Unity.Collections.NativeArray<Unity.Entities.Entity>`  

```csharp
private NativeArray<Entity> GetSortedFollowedCitizens()
	{
		NativeArray<Entity> nativeArray = m_FollowedQuery.ToEntityArray(Allocator.Temp);
		nativeArray.Sort(new FollowedCitizenComparer(base.EntityManager));
		return nativeArray;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LifePathEventSystem = base.World.GetOrCreateSystemManaged<LifePathEventSystem>();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_SelectedInfoUISystem = base.World.GetOrCreateSystemManaged<SelectedInfoUISystem>();
		m_ChirperUISystem = base.World.GetOrCreateSystemManaged<ChirperUISystem>();
		m_FollowedQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<Followed>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_HappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		AddBinding(m_FollowedCitizensBinding = new RawValueBinding("lifePath", "followedCitizens", BindFollowedCitizens));
		AddBinding(m_LifePathDetailsBinding = new RawMapBinding<Entity>("lifePath", "lifePathDetails", delegate(IJsonWriter binder, Entity citizen)
		{
			BindLifePathDetails(binder, citizen);
		}));
		AddBinding(m_LifePathItemsBinding = new RawMapBinding<Entity>("lifePath", "lifePathItems", delegate(IJsonWriter binder, Entity citizen)
		{
			BindLifePathItems(binder, citizen);
		}));
		AddBinding(new TriggerBinding<Entity>("lifePath", "followCitizen", FollowCitizen));
		AddBinding(new TriggerBinding<Entity>("lifePath", "unfollowCitizen", UnfollowCitizen));
		AddBinding(new ValueBinding<int>("lifePath", "maxFollowedCitizens", LifePathEventSystem.kMaxFollowed));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		int componentOrderVersion = base.EntityManager.GetComponentOrderVersion<Followed>();
		if (m_FollowedVersion != componentOrderVersion)
		{
			m_FollowedCitizensBinding.Update();
			m_LifePathDetailsBinding.UpdateAll();
			m_FollowedVersion = componentOrderVersion;
		}
		int componentOrderVersion2 = base.EntityManager.GetComponentOrderVersion<LifePathEntry>();
		int componentOrderVersion3 = base.EntityManager.GetComponentOrderVersion<Game.Triggers.Chirp>();
		if (m_LifePathEntryVersion != componentOrderVersion2 || m_ChirpVersion != componentOrderVersion3)
		{
			m_LifePathItemsBinding.UpdateAll();
			m_LifePathEntryVersion = componentOrderVersion2;
			m_ChirpVersion = componentOrderVersion3;
		}
	}
```

- `private UnfollowCitizen(Unity.Entities.Entity citizen) : System.Void`  

```csharp
private void UnfollowCitizen(Entity citizen)
	{
		m_LifePathEventSystem.UnfollowCitizen(citizen);
		m_SelectedInfoUISystem.SetDirty();
	}
```


## Nested types

- `Game.UI.InGame.LifePathUISystem+FollowedCitizenComparer`  

