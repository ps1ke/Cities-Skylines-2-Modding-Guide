# Game.Citizens.CitizenUtils

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static GetCitizenPrefabFromCitizen(Unity.Collections.NativeList<Unity.Entities.Entity> citizenPrefabs, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Prefabs.CitizenData> citizenDatas, Unity.Mathematics.Random rnd) : Unity.Entities.Entity`  
- `public static GetCitizenSelectedSound(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.Entity citizenPrefabRef) : Unity.Entities.Entity`  
- `public static GetHappinessKey(System.Int32 happiness) : Game.Citizens.CitizenHappiness`  
- `public static GetPathfindWeights(Game.Citizens.Citizen citizen, Game.Citizens.Household household, System.Int32 householdCitizens) : Game.Pathfind.PathfindWeights`  
- `public static HasMovedIn(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdDatas) : System.Boolean`  
- `public static HasMovedIn(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HouseholdMember, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdMembers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& households, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds) : System.Boolean`  
- `public static HouseholdMoveAway(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey, Unity.Entities.Entity householdEntity) : System.Void`  
- `public static HouseholdMoveAway(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.Entity householdEntity) : System.Void`  
- `public static IsCommuter(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Boolean`  
- `public static IsCorpsePickedByHearse(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposes) : System.Boolean`  
- `public static IsCorpsePickedByHearse(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen) : System.Boolean`  
- `public static IsDead(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems) : System.Boolean`  
- `public static IsDead(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen) : System.Boolean`  
- `public static IsDead(Game.Citizens.HealthProblem healthProblem) : System.Boolean`  
- `public static IsHouseholdNeedSupport(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : System.Boolean`  
- `public static IsResident(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen& citizen) : System.Boolean`  
- `public static IsResident(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> householdMemberFromEntity, Unity.Entities.ComponentLookup<Game.Agents.MovingAway> movingAwayFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> touristHouseholdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.CommuterHousehold> commuterHouseholdFromEntity) : System.Boolean`  
- `public static IsWorkableCitizen(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_Students, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems) : System.Boolean`  
- `public static TryGetResident(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Game.Citizens.Citizen& citizen) : System.Boolean`  

