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
public CitizenSection();
```


## Methods

- `private GetDestination() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetDestination();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


