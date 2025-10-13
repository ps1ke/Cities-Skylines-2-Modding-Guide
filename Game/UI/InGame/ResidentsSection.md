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
public ResidentsSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetAgeData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens) : Game.UI.InGame.AgeData`  

```csharp
private Game.UI.InGame.AgeData GetAgeData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens);
```

- `private GetEducationData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens) : Game.UI.InGame.EducationData`  

```csharp
private Game.UI.InGame.EducationData GetEducationData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
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

- `private static TryCountHouseholds(System.Int32& residentCount, System.Int32& petCount, System.Int32& householdCount, System.Int32& maxHouseholds, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkLookup, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandonedLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyDataLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblemLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposeLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdLookup, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizenLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdAnimal, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdAnimalLookup, Unity.Collections.NativeList<Unity.Entities.Entity> householdsResult) : System.Boolean`  

```csharp
private static System.Boolean TryCountHouseholds(System.Int32& residentCount, System.Int32& petCount, System.Int32& householdCount, System.Int32& maxHouseholds, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkLookup, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandonedLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyDataLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblemLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposeLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdLookup, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizenLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdAnimal, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdAnimalLookup, Unity.Collections.NativeList<Unity.Entities.Entity> householdsResult);
```


## Nested types

- `Game.UI.InGame.ResidentsSection+Result`  
- `Game.UI.InGame.ResidentsSection+CountHouseholdsJob`  
- `Game.UI.InGame.ResidentsSection+CountDistrictHouseholdsJob`  
- `Game.UI.InGame.ResidentsSection+TypeHandle`  

