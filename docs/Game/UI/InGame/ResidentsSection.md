# Game.UI.InGame.ResidentsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <isHousehold>k__BackingField`  
- `private System.Int32 <householdCount>k__BackingField`  
- `private System.Int32 <maxHouseholds>k__BackingField`  
- `private Game.UI.InGame.HouseholdWealthKey <wealthKey>k__BackingField`  
- `private System.Int32 <residentCount>k__BackingField`  
- `private System.Int32 <petCount>k__BackingField`  
- `private Unity.Entities.Entity <residenceEntity>k__BackingField`  
- `private Game.UI.InGame.CitizenResidenceKey <residenceKey>k__BackingField`  
- `private Game.UI.InGame.EducationData <educationData>k__BackingField`  
- `private Game.UI.InGame.AgeData <ageData>k__BackingField`  
- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  
- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  
- `private Unity.Collections.NativeArray<System.Int32> m_Results`  
- `private Colossal.Collections.NativeValue<Unity.Entities.Entity> m_ResidenceResult`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult`  
- `private Game.UI.InGame.ResidentsSection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Boolean isHousehold { private get; private set }`  
- `private System.Int32 householdCount { private get; private set }`  
- `private System.Int32 maxHouseholds { private get; private set }`  
- `private Game.UI.InGame.HouseholdWealthKey wealthKey { private get; private set }`  
- `private System.Int32 residentCount { private get; private set }`  
- `private System.Int32 petCount { private get; private set }`  
- `private Unity.Entities.Entity residenceEntity { private get; private set }`  
- `private Game.UI.InGame.CitizenResidenceKey residenceKey { private get; private set }`  
- `private Game.UI.InGame.EducationData educationData { private get; private set }`  
- `private Game.UI.InGame.AgeData ageData { private get; private set }`  

## Constructors

- `public ResidentsSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetAgeData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens) : Game.UI.InGame.AgeData`  
- `private GetEducationData(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens) : Game.UI.InGame.EducationData`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private static TryCountHouseholds(System.Int32& residentCount, System.Int32& petCount, System.Int32& householdCount, System.Int32& maxHouseholds, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkLookup, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandonedLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyDataLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblemLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposeLookup, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdLookup, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizenLookup, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdAnimal, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdAnimalLookup, Unity.Collections.NativeList<Unity.Entities.Entity> householdsResult) : System.Boolean`  

## Nested types

- `Game.UI.InGame.ResidentsSection+Result`  
- `Game.UI.InGame.ResidentsSection+CountHouseholdsJob`  
- `Game.UI.InGame.ResidentsSection+CountDistrictHouseholdsJob`  
- `Game.UI.InGame.ResidentsSection+TypeHandle`  

