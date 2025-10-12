# Game.UI.InGame.CitizenUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static GetAge(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenAgeKey`  
- `public static GetAverageHouseholdWealth(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeList<Unity.Entities.Entity> households, Game.Prefabs.CitizenHappinessParameterData happinessParameters) : Game.UI.InGame.HouseholdWealthKey`  
- `public static GetCitizenConditions(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Citizens.HouseholdMember householdMember, Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions) : Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition>`  
- `public static GetCitizenHappiness(Game.Citizens.Citizen citizen) : Game.UI.InGame.CitizenHappiness`  
- `public static GetCitizenHappiness(System.Int32 happiness) : Game.UI.InGame.CitizenHappiness`  
- `public static GetCompanyEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity) : Unity.Entities.Entity`  
- `public static GetEducation(Game.Citizens.Citizen citizen) : Game.UI.InGame.CitizenEducationKey`  
- `public static GetHouseholdWealth(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity, Game.Prefabs.CitizenHappinessParameterData happinessParameters) : Game.UI.InGame.HouseholdWealthKey`  
- `public static GetJobLevel(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenJobLevelKey`  
- `public static GetOccupation(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenOccupationKey`  
- `public static GetResidenceEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity) : Unity.Entities.Entity`  
- `public static GetResidenceType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenResidenceKey`  
- `public static GetSchoolEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity, System.Int32& level) : Unity.Entities.Entity`  
- `public static GetStateKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenStateKey`  
- `public static GetWorkplaceEntity(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizenEntity) : Unity.Entities.Entity`  
- `public static GetWorkplaceType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.UI.InGame.CitizenWorkplaceKey`  
- `private static PathEndReached(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen) : System.Boolean`  
- `private static TryGetTravelPurpose(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Purpose& purpose) : System.Boolean`  

