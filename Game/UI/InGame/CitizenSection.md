# Game.UI.InGame.CitizenSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.CitizenKey <citizenKey>k__BackingField;
    private Game.UI.InGame.CitizenStateKey <stateKey>k__BackingField;
    private Unity.Entities.Entity <householdEntity>k__BackingField;
    private Unity.Entities.Entity <residenceEntity>k__BackingField;
    private Game.UI.InGame.CitizenResidenceKey <residenceKey>k__BackingField;
    private Unity.Entities.Entity <workplaceEntity>k__BackingField;
    private Unity.Entities.Entity <companyEntity>k__BackingField;
    private Game.UI.InGame.CitizenWorkplaceKey <workplaceKey>k__BackingField;
    private Game.UI.InGame.CitizenOccupationKey <occupationKey>k__BackingField;
    private Game.UI.InGame.CitizenJobLevelKey <jobLevelKey>k__BackingField;
    private Unity.Entities.Entity <schoolEntity>k__BackingField;
    private System.Int32 <schoolLevel>k__BackingField;
    private Game.UI.InGame.CitizenEducationKey <educationKey>k__BackingField;
    private Game.UI.InGame.CitizenAgeKey <ageKey>k__BackingField;
    private Game.UI.InGame.HouseholdWealthKey <wealthKey>k__BackingField;
    private Unity.Entities.Entity <destinationEntity>k__BackingField;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;

    protected System.String group { protected get; }
    private Game.UI.InGame.CitizenKey citizenKey { private get; private set; }
    private Game.UI.InGame.CitizenStateKey stateKey { private get; private set; }
    private Unity.Entities.Entity householdEntity { private get; private set; }
    private Unity.Entities.Entity residenceEntity { private get; private set; }
    private Game.UI.InGame.CitizenResidenceKey residenceKey { private get; private set; }
    private Unity.Entities.Entity workplaceEntity { private get; private set; }
    private Unity.Entities.Entity companyEntity { private get; private set; }
    private Game.UI.InGame.CitizenWorkplaceKey workplaceKey { private get; private set; }
    private Game.UI.InGame.CitizenOccupationKey occupationKey { private get; private set; }
    private Game.UI.InGame.CitizenJobLevelKey jobLevelKey { private get; private set; }
    private Unity.Entities.Entity schoolEntity { private get; private set; }
    private System.Int32 schoolLevel { private get; private set; }
    private Game.UI.InGame.CitizenEducationKey educationKey { private get; private set; }
    private Game.UI.InGame.CitizenAgeKey ageKey { private get; private set; }
    private Game.UI.InGame.HouseholdWealthKey wealthKey { private get; private set; }
    private Unity.Entities.Entity destinationEntity { private get; private set; }

    public CitizenSection();

    private Unity.Entities.Entity GetDestination();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.CitizenKey <citizenKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenKey <citizenKey>k__BackingField;
```

- `private Game.UI.InGame.CitizenStateKey <stateKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenStateKey <stateKey>k__BackingField;
```

- `private Unity.Entities.Entity <householdEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <householdEntity>k__BackingField;
```

- `private Unity.Entities.Entity <residenceEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <residenceEntity>k__BackingField;
```

- `private Game.UI.InGame.CitizenResidenceKey <residenceKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenResidenceKey <residenceKey>k__BackingField;
```

- `private Unity.Entities.Entity <workplaceEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <workplaceEntity>k__BackingField;
```

- `private Unity.Entities.Entity <companyEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <companyEntity>k__BackingField;
```

- `private Game.UI.InGame.CitizenWorkplaceKey <workplaceKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenWorkplaceKey <workplaceKey>k__BackingField;
```

- `private Game.UI.InGame.CitizenOccupationKey <occupationKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenOccupationKey <occupationKey>k__BackingField;
```

- `private Game.UI.InGame.CitizenJobLevelKey <jobLevelKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenJobLevelKey <jobLevelKey>k__BackingField;
```

- `private Unity.Entities.Entity <schoolEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <schoolEntity>k__BackingField;
```

- `private System.Int32 <schoolLevel>k__BackingField`  

```csharp
private System.Int32 <schoolLevel>k__BackingField;
```

- `private Game.UI.InGame.CitizenEducationKey <educationKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenEducationKey <educationKey>k__BackingField;
```

- `private Game.UI.InGame.CitizenAgeKey <ageKey>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenAgeKey <ageKey>k__BackingField;
```

- `private Game.UI.InGame.HouseholdWealthKey <wealthKey>k__BackingField`  

```csharp
private Game.UI.InGame.HouseholdWealthKey <wealthKey>k__BackingField;
```

- `private Unity.Entities.Entity <destinationEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <destinationEntity>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.CitizenKey citizenKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenKey citizenKey { private get; private set; }
```

- `private Game.UI.InGame.CitizenStateKey stateKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenStateKey stateKey { private get; private set; }
```

- `private Unity.Entities.Entity householdEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity householdEntity { private get; private set; }
```

- `private Unity.Entities.Entity residenceEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity residenceEntity { private get; private set; }
```

- `private Game.UI.InGame.CitizenResidenceKey residenceKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenResidenceKey residenceKey { private get; private set; }
```

- `private Unity.Entities.Entity workplaceEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity workplaceEntity { private get; private set; }
```

- `private Unity.Entities.Entity companyEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity companyEntity { private get; private set; }
```

- `private Game.UI.InGame.CitizenWorkplaceKey workplaceKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenWorkplaceKey workplaceKey { private get; private set; }
```

- `private Game.UI.InGame.CitizenOccupationKey occupationKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenOccupationKey occupationKey { private get; private set; }
```

- `private Game.UI.InGame.CitizenJobLevelKey jobLevelKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenJobLevelKey jobLevelKey { private get; private set; }
```

- `private Unity.Entities.Entity schoolEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity schoolEntity { private get; private set; }
```

- `private System.Int32 schoolLevel { private get; private set }`  

```csharp
private System.Int32 schoolLevel { private get; private set; }
```

- `private Game.UI.InGame.CitizenEducationKey educationKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenEducationKey educationKey { private get; private set; }
```

- `private Game.UI.InGame.CitizenAgeKey ageKey { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenAgeKey ageKey { private get; private set; }
```

- `private Game.UI.InGame.HouseholdWealthKey wealthKey { private get; private set }`  

```csharp
private Game.UI.InGame.HouseholdWealthKey wealthKey { private get; private set; }
```

- `private Unity.Entities.Entity destinationEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity destinationEntity { private get; private set; }
```


## Constructors

- `public CitizenSection()`  

```csharp
[Preserve]
	public CitizenSection()
	{
	}
```


## Methods

- `private GetDestination() : Unity.Entities.Entity`  

```csharp
private Entity GetDestination()
	{
		if (base.EntityManager.TryGetComponent<CurrentTransport>(selectedEntity, out var component))
		{
			Entity entity = Entity.Null;
			if (base.EntityManager.TryGetComponent<Divert>(component.m_CurrentTransport, out var component2))
			{
				Purpose purpose = component2.m_Purpose;
				if (purpose == Purpose.Safety || purpose == Purpose.Shopping || purpose == Purpose.SendMail)
				{
					entity = component2.m_Target;
				}
			}
			if (entity == Entity.Null && base.EntityManager.TryGetComponent<Target>(component.m_CurrentTransport, out var component3))
			{
				entity = component3.m_Target;
			}
			if (base.EntityManager.HasComponent<Game.Objects.OutsideConnection>(entity))
			{
				return entity;
			}
			if (base.EntityManager.TryGetComponent<Owner>(entity, out var component4))
			{
				return component4.m_Owner;
			}
			if (base.EntityManager.Exists(entity))
			{
				return entity;
			}
		}
		return Entity.Null;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_HappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		RequireForUpdate(m_HappinessParameterQuery);
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Citizen componentData = base.EntityManager.GetComponentData<Citizen>(selectedEntity);
		if (base.EntityManager.TryGetComponent<HouseholdMember>(selectedEntity, out var component))
		{
			householdEntity = component.m_Household;
			citizenKey = CitizenKey.Citizen;
			if (base.EntityManager.HasComponent<CommuterHousehold>(component.m_Household))
			{
				citizenKey = CitizenKey.Commuter;
			}
			else if (base.EntityManager.HasComponent<TouristHousehold>(component.m_Household))
			{
				citizenKey = CitizenKey.Tourist;
			}
			wealthKey = CitizenUIUtils.GetHouseholdWealth(base.EntityManager, householdEntity, m_HappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>());
		}
		stateKey = CitizenUIUtils.GetStateKey(base.EntityManager, selectedEntity);
		residenceEntity = CitizenUIUtils.GetResidenceEntity(base.EntityManager, selectedEntity);
		residenceKey = CitizenUIUtils.GetResidenceType(base.EntityManager, selectedEntity);
		workplaceEntity = CitizenUIUtils.GetWorkplaceEntity(base.EntityManager, selectedEntity);
		companyEntity = CitizenUIUtils.GetCompanyEntity(base.EntityManager, selectedEntity);
		workplaceKey = CitizenUIUtils.GetWorkplaceType(base.EntityManager, selectedEntity);
		schoolEntity = CitizenUIUtils.GetSchoolEntity(base.EntityManager, selectedEntity, out var level);
		schoolLevel = level;
		occupationKey = CitizenUIUtils.GetOccupation(base.EntityManager, selectedEntity);
		jobLevelKey = CitizenUIUtils.GetJobLevel(base.EntityManager, selectedEntity);
		ageKey = CitizenUIUtils.GetAge(base.EntityManager, selectedEntity);
		educationKey = CitizenUIUtils.GetEducation(componentData);
		destinationEntity = GetDestination();
		if ((componentData.m_State & CitizenFlags.Male) != CitizenFlags.None)
		{
			base.tooltipTags.Add(TooltipTags.Male.ToString());
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("citizenKey");
		writer.Write(Enum.GetName(typeof(CitizenKey), citizenKey));
		writer.PropertyName("stateKey");
		writer.Write(Enum.GetName(typeof(CitizenStateKey), stateKey));
		writer.PropertyName("household");
		if (householdEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, householdEntity);
		}
		writer.PropertyName("householdEntity");
		if (householdEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(householdEntity);
		}
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
		writer.PropertyName("workplace");
		if (companyEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, companyEntity);
		}
		writer.PropertyName("workplaceEntity");
		if (workplaceEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(workplaceEntity);
		}
		writer.PropertyName("workplaceKey");
		writer.Write(Enum.GetName(typeof(CitizenWorkplaceKey), workplaceKey));
		writer.PropertyName("occupationKey");
		writer.Write(Enum.GetName(typeof(CitizenOccupationKey), occupationKey));
		writer.PropertyName("jobLevelKey");
		writer.Write(Enum.GetName(typeof(CitizenJobLevelKey), jobLevelKey));
		writer.PropertyName("school");
		if (schoolEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, schoolEntity);
		}
		writer.PropertyName("schoolEntity");
		if (schoolEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(schoolEntity);
		}
		writer.PropertyName("schoolLevel");
		writer.Write(schoolLevel);
		writer.PropertyName("educationKey");
		writer.Write(Enum.GetName(typeof(CitizenEducationKey), educationKey));
		writer.PropertyName("ageKey");
		writer.Write(Enum.GetName(typeof(CitizenAgeKey), ageKey));
		writer.PropertyName("wealthKey");
		writer.Write(Enum.GetName(typeof(HouseholdWealthKey), wealthKey));
		writer.PropertyName("destination");
		if (destinationEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, destinationEntity);
		}
		writer.PropertyName("destinationEntity");
		if (destinationEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(destinationEntity);
		}
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		householdEntity = Entity.Null;
		residenceEntity = Entity.Null;
		workplaceEntity = Entity.Null;
		schoolEntity = Entity.Null;
		destinationEntity = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<HouseholdMember>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Citizen>(selectedEntity);
		}
		return false;
	}
```


