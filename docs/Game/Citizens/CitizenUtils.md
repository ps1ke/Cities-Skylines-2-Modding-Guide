# Game.Citizens.CitizenUtils

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CitizenUtils
{
    public static Unity.Entities.Entity GetCitizenPrefabFromCitizen(Unity.Collections.NativeList<Unity.Entities.Entity> citizenPrefabs, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Prefabs.CitizenData> citizenDatas, Unity.Mathematics.Random rnd);
    public static Unity.Entities.Entity GetCitizenSelectedSound(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.Entity citizenPrefabRef);
    public static Game.Citizens.CitizenHappiness GetHappinessKey(System.Int32 happiness);
    public static Game.Pathfind.PathfindWeights GetPathfindWeights(Game.Citizens.Citizen citizen, Game.Citizens.Household household, System.Int32 householdCitizens);
    public static System.Boolean HasMovedIn(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdDatas);
    public static System.Boolean HasMovedIn(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HouseholdMember, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdMembers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& households, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds);
    public static System.Void HouseholdMoveAway(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey, Unity.Entities.Entity householdEntity);
    public static System.Void HouseholdMoveAway(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.Entity householdEntity);
    public static System.Boolean IsCommuter(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
    public static System.Boolean IsCorpsePickedByHearse(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposes);
    public static System.Boolean IsCorpsePickedByHearse(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen);
    public static System.Boolean IsDead(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems);
    public static System.Boolean IsDead(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen);
    public static System.Boolean IsDead(Game.Citizens.HealthProblem healthProblem);
    public static System.Boolean IsHouseholdNeedSupport(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students);
    public static System.Boolean IsResident(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen& citizen);
    public static System.Boolean IsResident(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> householdMemberFromEntity, Unity.Entities.ComponentLookup<Game.Agents.MovingAway> movingAwayFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> touristHouseholdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.CommuterHousehold> commuterHouseholdFromEntity);
    public static System.Boolean IsWorkableCitizen(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_Students, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems);
    public static System.Boolean TryGetResident(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Game.Citizens.Citizen& citizen);
}
```


## Methods

- `public static GetCitizenPrefabFromCitizen(Unity.Collections.NativeList<Unity.Entities.Entity> citizenPrefabs, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Prefabs.CitizenData> citizenDatas, Unity.Mathematics.Random rnd) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetCitizenPrefabFromCitizen(Unity.Collections.NativeList<Unity.Entities.Entity> citizenPrefabs, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Prefabs.CitizenData> citizenDatas, Unity.Mathematics.Random rnd);
```

- `public static GetCitizenSelectedSound(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.Entity citizenPrefabRef) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetCitizenSelectedSound(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.Entity citizenPrefabRef);
```

- `public static GetHappinessKey(System.Int32 happiness) : Game.Citizens.CitizenHappiness`  

```csharp
public static Game.Citizens.CitizenHappiness GetHappinessKey(System.Int32 happiness);
```

- `public static GetPathfindWeights(Game.Citizens.Citizen citizen, Game.Citizens.Household household, System.Int32 householdCitizens) : Game.Pathfind.PathfindWeights`  

```csharp
public static Game.Pathfind.PathfindWeights GetPathfindWeights(Game.Citizens.Citizen citizen, Game.Citizens.Household household, System.Int32 householdCitizens);
```

- `public static HasMovedIn(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdDatas) : System.Boolean`  

```csharp
public static System.Boolean HasMovedIn(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdDatas);
```

- `public static HasMovedIn(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HouseholdMember, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdMembers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& households, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds) : System.Boolean`  

```csharp
public static System.Boolean HasMovedIn(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HouseholdMember, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdMembers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& households, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds);
```

- `public static HouseholdMoveAway(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey, Unity.Entities.Entity householdEntity) : System.Void`  

```csharp
public static System.Void HouseholdMoveAway(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey, Unity.Entities.Entity householdEntity);
```

- `public static HouseholdMoveAway(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.Entity householdEntity) : System.Void`  

```csharp
public static System.Void HouseholdMoveAway(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.Entity householdEntity);
```

- `public static IsCommuter(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Boolean`  

```csharp
public static System.Boolean IsCommuter(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
```

- `public static IsCorpsePickedByHearse(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposes) : System.Boolean`  

```csharp
public static System.Boolean IsCorpsePickedByHearse(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposes);
```

- `public static IsCorpsePickedByHearse(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
public static System.Boolean IsCorpsePickedByHearse(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen);
```

- `public static IsDead(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems) : System.Boolean`  

```csharp
public static System.Boolean IsDead(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems);
```

- `public static IsDead(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
public static System.Boolean IsDead(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen);
```

- `public static IsDead(Game.Citizens.HealthProblem healthProblem) : System.Boolean`  

```csharp
public static System.Boolean IsDead(Game.Citizens.HealthProblem healthProblem);
```

- `public static IsHouseholdNeedSupport(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : System.Boolean`  

```csharp
public static System.Boolean IsHouseholdNeedSupport(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students);
```

- `public static IsResident(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen& citizen) : System.Boolean`  

```csharp
public static System.Boolean IsResident(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen& citizen);
```

- `public static IsResident(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> householdMemberFromEntity, Unity.Entities.ComponentLookup<Game.Agents.MovingAway> movingAwayFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> touristHouseholdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.CommuterHousehold> commuterHouseholdFromEntity) : System.Boolean`  

```csharp
public static System.Boolean IsResident(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> householdMemberFromEntity, Unity.Entities.ComponentLookup<Game.Agents.MovingAway> movingAwayFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> touristHouseholdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.CommuterHousehold> commuterHouseholdFromEntity);
```

- `public static IsWorkableCitizen(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_Students, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems) : System.Boolean`  

```csharp
public static System.Boolean IsWorkableCitizen(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_Students, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems);
```

- `public static TryGetResident(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Game.Citizens.Citizen& citizen) : System.Boolean`  

```csharp
public static System.Boolean TryGetResident(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Game.Citizens.Citizen& citizen);
```


