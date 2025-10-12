# Game.UI.InGame.CitizenSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.CitizenKey <citizenKey>k__BackingField`  
- `private Game.UI.InGame.CitizenStateKey <stateKey>k__BackingField`  
- `private Unity.Entities.Entity <householdEntity>k__BackingField`  
- `private Unity.Entities.Entity <residenceEntity>k__BackingField`  
- `private Game.UI.InGame.CitizenResidenceKey <residenceKey>k__BackingField`  
- `private Unity.Entities.Entity <workplaceEntity>k__BackingField`  
- `private Unity.Entities.Entity <companyEntity>k__BackingField`  
- `private Game.UI.InGame.CitizenWorkplaceKey <workplaceKey>k__BackingField`  
- `private Game.UI.InGame.CitizenOccupationKey <occupationKey>k__BackingField`  
- `private Game.UI.InGame.CitizenJobLevelKey <jobLevelKey>k__BackingField`  
- `private Unity.Entities.Entity <schoolEntity>k__BackingField`  
- `private System.Int32 <schoolLevel>k__BackingField`  
- `private Game.UI.InGame.CitizenEducationKey <educationKey>k__BackingField`  
- `private Game.UI.InGame.CitizenAgeKey <ageKey>k__BackingField`  
- `private Game.UI.InGame.HouseholdWealthKey <wealthKey>k__BackingField`  
- `private Unity.Entities.Entity <destinationEntity>k__BackingField`  
- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

## Properties

- `protected System.String group { protected get }`  
- `private Game.UI.InGame.CitizenKey citizenKey { private get; private set }`  
- `private Game.UI.InGame.CitizenStateKey stateKey { private get; private set }`  
- `private Unity.Entities.Entity householdEntity { private get; private set }`  
- `private Unity.Entities.Entity residenceEntity { private get; private set }`  
- `private Game.UI.InGame.CitizenResidenceKey residenceKey { private get; private set }`  
- `private Unity.Entities.Entity workplaceEntity { private get; private set }`  
- `private Unity.Entities.Entity companyEntity { private get; private set }`  
- `private Game.UI.InGame.CitizenWorkplaceKey workplaceKey { private get; private set }`  
- `private Game.UI.InGame.CitizenOccupationKey occupationKey { private get; private set }`  
- `private Game.UI.InGame.CitizenJobLevelKey jobLevelKey { private get; private set }`  
- `private Unity.Entities.Entity schoolEntity { private get; private set }`  
- `private System.Int32 schoolLevel { private get; private set }`  
- `private Game.UI.InGame.CitizenEducationKey educationKey { private get; private set }`  
- `private Game.UI.InGame.CitizenAgeKey ageKey { private get; private set }`  
- `private Game.UI.InGame.HouseholdWealthKey wealthKey { private get; private set }`  
- `private Unity.Entities.Entity destinationEntity { private get; private set }`  

## Constructors

- `public CitizenSection()`  

## Methods

- `private GetDestination() : Unity.Entities.Entity`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

