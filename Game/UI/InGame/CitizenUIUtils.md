# Game.UI.InGame.CitizenUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CitizenUIUtils
{
    public static Game.UI.InGame.CitizenAgeKey GetAge(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static Game.UI.InGame.HouseholdWealthKey GetAverageHouseholdWealth(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeList<Unity.Entities.Entity> households, Game.Prefabs.CitizenHappinessParameterData happinessParameters);
    public static Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> GetCitizenConditions(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Citizens.HouseholdMember householdMember, Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions);
    public static Game.UI.InGame.CitizenHappiness GetCitizenHappiness(Game.Citizens.Citizen citizen);
    public static Game.UI.InGame.CitizenHappiness GetCitizenHappiness(System.Int32 happiness);
    public static Unity.Entities.Entity GetCompanyEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity);
    public static Game.UI.InGame.CitizenEducationKey GetEducation(Game.Citizens.Citizen citizen);
    public static Game.UI.InGame.HouseholdWealthKey GetHouseholdWealth(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity, Game.Prefabs.CitizenHappinessParameterData happinessParameters);
    public static Game.UI.InGame.CitizenJobLevelKey GetJobLevel(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static Game.UI.InGame.CitizenOccupationKey GetOccupation(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static Unity.Entities.Entity GetResidenceEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity);
    public static Game.UI.InGame.CitizenResidenceKey GetResidenceType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static Unity.Entities.Entity GetSchoolEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity, System.Int32& level);
    public static Game.UI.InGame.CitizenStateKey GetStateKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static Unity.Entities.Entity GetWorkplaceEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity);
    public static Game.UI.InGame.CitizenWorkplaceKey GetWorkplaceType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    private static System.Boolean PathEndReached(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen);
    private static System.Boolean TryGetTravelPurpose(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Purpose& purpose);
}
```


## Methods

- `public static GetAge(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenAgeKey`  

```csharp
public static Game.UI.InGame.CitizenAgeKey GetAge(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static GetAverageHouseholdWealth(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeList<Unity.Entities.Entity> households, Game.Prefabs.CitizenHappinessParameterData happinessParameters) : Game.UI.InGame.HouseholdWealthKey`  

```csharp
public static Game.UI.InGame.HouseholdWealthKey GetAverageHouseholdWealth(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeList<Unity.Entities.Entity> households, Game.Prefabs.CitizenHappinessParameterData happinessParameters);
```

- `public static GetCitizenConditions(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Citizens.HouseholdMember householdMember, Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions) : Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> GetCitizenConditions(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Citizens.HouseholdMember householdMember, Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions);
```

- `public static GetCitizenHappiness(Game.Citizens.Citizen citizen) : Game.UI.InGame.CitizenHappiness`  

```csharp
public static Game.UI.InGame.CitizenHappiness GetCitizenHappiness(Game.Citizens.Citizen citizen);
```

- `public static GetCitizenHappiness(System.Int32 happiness) : Game.UI.InGame.CitizenHappiness`  

```csharp
public static Game.UI.InGame.CitizenHappiness GetCitizenHappiness(System.Int32 happiness);
```

- `public static GetCompanyEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetCompanyEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity);
```

- `public static GetEducation(Game.Citizens.Citizen citizen) : Game.UI.InGame.CitizenEducationKey`  

```csharp
public static Game.UI.InGame.CitizenEducationKey GetEducation(Game.Citizens.Citizen citizen);
```

- `public static GetHouseholdWealth(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity, Game.Prefabs.CitizenHappinessParameterData happinessParameters) : Game.UI.InGame.HouseholdWealthKey`  

```csharp
public static Game.UI.InGame.HouseholdWealthKey GetHouseholdWealth(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity, Game.Prefabs.CitizenHappinessParameterData happinessParameters);
```

- `public static GetJobLevel(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenJobLevelKey`  

```csharp
public static Game.UI.InGame.CitizenJobLevelKey GetJobLevel(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static GetOccupation(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenOccupationKey`  

```csharp
public static Game.UI.InGame.CitizenOccupationKey GetOccupation(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static GetResidenceEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetResidenceEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity);
```

- `public static GetResidenceType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenResidenceKey`  

```csharp
public static Game.UI.InGame.CitizenResidenceKey GetResidenceType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static GetSchoolEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity, System.Int32& level) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetSchoolEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity, System.Int32& level);
```

- `public static GetStateKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenStateKey`  

```csharp
public static Game.UI.InGame.CitizenStateKey GetStateKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static GetWorkplaceEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetWorkplaceEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity);
```

- `public static GetWorkplaceType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenWorkplaceKey`  

```csharp
public static Game.UI.InGame.CitizenWorkplaceKey GetWorkplaceType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `private static PathEndReached(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
private static System.Boolean PathEndReached(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen);
```

- `private static TryGetTravelPurpose(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Purpose& purpose) : System.Boolean`  

```csharp
private static System.Boolean TryGetTravelPurpose(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Purpose& purpose);
```


