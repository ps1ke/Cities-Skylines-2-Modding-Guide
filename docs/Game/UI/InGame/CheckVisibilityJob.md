# Game.UI.InGame.HouseholdSidebarSection+CheckVisibilityJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CheckVisibilityJob : Unity.Jobs.IJob
{
    public Unity.Entities.Entity m_SelectedEntity;
    public Unity.Entities.Entity m_SelectedPrefab;
    public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingLookup;
    public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup;
    public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkFromLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.HouseholdPet> m_HouseholdPetLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup;
    public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup;
    public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup;
    public Unity.Collections.NativeArray<System.Int32> m_Results;

    public System.Void Execute();
    private System.Boolean HasResidentialProperties(System.Int32& residentCount, System.Int32& householdCount, Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
}
```


## Fields

- `public Unity.Entities.Entity m_SelectedEntity`  

```csharp
public Unity.Entities.Entity m_SelectedEntity;
```

- `public Unity.Entities.Entity m_SelectedPrefab`  

```csharp
public Unity.Entities.Entity m_SelectedPrefab;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkFromLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkFromLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.HouseholdPet> m_HouseholdPetLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.HouseholdPet> m_HouseholdPetLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup;
```

- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup`  

```csharp
public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Results;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private HasResidentialProperties(System.Int32& residentCount, System.Int32& householdCount, Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasResidentialProperties(System.Int32& residentCount, System.Int32& householdCount, Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```


