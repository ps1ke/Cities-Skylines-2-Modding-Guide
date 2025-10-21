# Game.UI.InGame.ResidentsSection+CountHouseholdsJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CountHouseholdsJob : Unity.Jobs.IJob
{
    public Unity.Entities.Entity m_SelectedEntity;
    public Unity.Entities.Entity m_SelectedPrefab;
    public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkLookup;
    public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingLookup;
    public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> m_HomelessHouseholdLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup;
    public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenterLookup;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup;
    public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup;
    public Unity.Entities.BufferLookup<Game.Citizens.HouseholdAnimal> m_HouseholdAnimalLookup;
    public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup;
    public Unity.Collections.NativeArray<System.Int32> m_Results;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult;
    public Colossal.Collections.NativeValue<Unity.Entities.Entity> m_ResidenceResult;

    public System.Void Execute();
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

- `public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> m_HomelessHouseholdLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> m_HomelessHouseholdLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenterLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenterLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup;
```

- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup`  

```csharp
public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup;
```

- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdAnimal> m_HouseholdAnimalLookup`  

```csharp
public Unity.Entities.BufferLookup<Game.Citizens.HouseholdAnimal> m_HouseholdAnimalLookup;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult;
```

- `public Colossal.Collections.NativeValue<Unity.Entities.Entity> m_ResidenceResult`  

```csharp
public Colossal.Collections.NativeValue<Unity.Entities.Entity> m_ResidenceResult;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


