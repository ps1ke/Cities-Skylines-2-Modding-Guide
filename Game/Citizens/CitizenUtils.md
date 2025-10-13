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
public static Entity GetCitizenPrefabFromCitizen(NativeList<Entity> citizenPrefabs, Citizen citizen, ComponentLookup<CitizenData> citizenDatas, Random rnd)
	{
		int num = 0;
		for (int i = 0; i < citizenPrefabs.Length; i++)
		{
			CitizenData citizenData = citizenDatas[citizenPrefabs[i]];
			if (((citizen.m_State & CitizenFlags.Male) == 0) ^ citizenData.m_Male)
			{
				num++;
			}
		}
		if (num > 0)
		{
			int num2 = rnd.NextInt(num);
			for (int j = 0; j < citizenPrefabs.Length; j++)
			{
				CitizenData citizenData2 = citizenDatas[citizenPrefabs[j]];
				if (((citizen.m_State & CitizenFlags.Male) == 0) ^ citizenData2.m_Male)
				{
					num2--;
					if (num2 < 0)
					{
						PrefabRef prefabRef = new PrefabRef
						{
							m_Prefab = citizenPrefabs[j]
						};
						return prefabRef.m_Prefab;
					}
				}
			}
		}
		return Entity.Null;
	}
```

- `public static GetCitizenSelectedSound(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.Entity citizenPrefabRef) : Unity.Entities.Entity`  

```csharp
public static Entity GetCitizenSelectedSound(EntityManager entityManager, Entity entity, Citizen citizen, Entity citizenPrefabRef)
	{
		if (!entityManager.HasComponent<CitizenSelectedSoundData>(citizenPrefabRef))
		{
			return Entity.Null;
		}
		CitizenHappiness happinessKey = GetHappinessKey(citizen.Happiness);
		bool isSickOrInjured = false;
		if (entityManager.TryGetComponent<HealthProblem>(entity, out var component) && (component.m_Flags & (HealthProblemFlags.Sick | HealthProblemFlags.Injured)) != HealthProblemFlags.None)
		{
			isSickOrInjured = true;
		}
		DynamicBuffer<CitizenSelectedSoundData> buffer = entityManager.GetBuffer<CitizenSelectedSoundData>(citizenPrefabRef, isReadOnly: true);
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i].Equals(new CitizenSelectedSoundData(isSickOrInjured, citizen.GetAge(), happinessKey, Entity.Null)))
			{
				return buffer[i].m_SelectedSound;
			}
		}
		return Entity.Null;
	}
```

- `public static GetHappinessKey(System.Int32 happiness) : Game.Citizens.CitizenHappiness`  

```csharp
public static CitizenHappiness GetHappinessKey(int happiness)
	{
		if (happiness > 70)
		{
			return CitizenHappiness.Happy;
		}
		if (happiness > 55)
		{
			return CitizenHappiness.Content;
		}
		if (happiness > 40)
		{
			return CitizenHappiness.Neutral;
		}
		if (happiness > 25)
		{
			return CitizenHappiness.Sad;
		}
		return CitizenHappiness.Depressed;
	}
```

- `public static GetPathfindWeights(Game.Citizens.Citizen citizen, Game.Citizens.Household household, System.Int32 householdCitizens) : Game.Pathfind.PathfindWeights`  

```csharp
public static PathfindWeights GetPathfindWeights(Citizen citizen, Household household, int householdCitizens)
	{
		float time = 5f * (4f - 3.75f * (float)(int)citizen.m_LeisureCounter / 255f);
		float behaviour = 2f;
		float num = 2500f * math.max(1f, householdCitizens) / (float)math.max(250, household.m_ConsumptionPerDay);
		float comfort = 1f + 2f * citizen.GetPseudoRandom(CitizenPseudoRandom.TrafficComfort).NextFloat();
		num = math.select(num, num * 0.1f, (household.m_Flags & HouseholdFlags.MovedIn) == 0 && (citizen.m_State & (CitizenFlags.MovingAwayReachOC | CitizenFlags.Tourist | CitizenFlags.Commuter)) == 0);
		return new PathfindWeights(time, behaviour, num, comfort);
	}
```

- `public static HasMovedIn(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdDatas) : System.Boolean`  

```csharp
public static bool HasMovedIn(Entity citizen, ref ComponentLookup<HouseholdMember> householdMembers, ref ComponentLookup<Household> households, ref ComponentLookup<HomelessHousehold> homelessHouseholds)
	{
		if (householdMembers.TryGetComponent(citizen, out var componentData) && households.TryGetComponent(componentData.m_Household, out var componentData2) && (componentData2.m_Flags & HouseholdFlags.MovedIn) != HouseholdFlags.None)
		{
			return !homelessHouseholds.HasComponent(componentData.m_Household);
		}
		return false;
	}
```

- `public static HasMovedIn(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HouseholdMember, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdMembers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& households, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds) : System.Boolean`  

```csharp
public static bool HasMovedIn(Entity citizen, ref ComponentLookup<HouseholdMember> householdMembers, ref ComponentLookup<Household> households, ref ComponentLookup<HomelessHousehold> homelessHouseholds)
	{
		if (householdMembers.TryGetComponent(citizen, out var componentData) && households.TryGetComponent(componentData.m_Household, out var componentData2) && (componentData2.m_Flags & HouseholdFlags.MovedIn) != HouseholdFlags.None)
		{
			return !homelessHouseholds.HasComponent(componentData.m_Household);
		}
		return false;
	}
```

- `public static HouseholdMoveAway(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey, Unity.Entities.Entity householdEntity) : System.Void`  

```csharp
public static void HouseholdMoveAway(EntityCommandBuffer commandBuffer, Entity householdEntity)
	{
		commandBuffer.AddComponent(householdEntity, default(MovingAway));
	}
```

- `public static HouseholdMoveAway(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.Entity householdEntity) : System.Void`  

```csharp
public static void HouseholdMoveAway(EntityCommandBuffer commandBuffer, Entity householdEntity)
	{
		commandBuffer.AddComponent(householdEntity, default(MovingAway));
	}
```

- `public static IsCommuter(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Boolean`  

```csharp
public static bool IsCommuter(Entity citizenEntity, ref ComponentLookup<Citizen> citizens)
	{
		return (citizens[citizenEntity].m_State & CitizenFlags.Commuter) != 0;
	}
```

- `public static IsCorpsePickedByHearse(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Citizens.TravelPurpose, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& travelPurposes) : System.Boolean`  

```csharp
public static bool IsCorpsePickedByHearse(EntityManager entityManager, Entity citizen)
	{
		if (IsDead(entityManager, citizen) && entityManager.TryGetComponent<TravelPurpose>(citizen, out var component) && (component.m_Purpose == Purpose.Deathcare || component.m_Purpose == Purpose.InDeathcare))
		{
			return true;
		}
		return false;
	}
```

- `public static IsCorpsePickedByHearse(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
public static bool IsCorpsePickedByHearse(EntityManager entityManager, Entity citizen)
	{
		if (IsDead(entityManager, citizen) && entityManager.TryGetComponent<TravelPurpose>(citizen, out var component) && (component.m_Purpose == Purpose.Deathcare || component.m_Purpose == Purpose.InDeathcare))
		{
			return true;
		}
		return false;
	}
```

- `public static IsDead(Unity.Entities.Entity citizen, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems) : System.Boolean`  

```csharp
public static bool IsDead(HealthProblem healthProblem)
	{
		return (healthProblem.m_Flags & HealthProblemFlags.Dead) != 0;
	}
```

- `public static IsDead(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
public static bool IsDead(HealthProblem healthProblem)
	{
		return (healthProblem.m_Flags & HealthProblemFlags.Dead) != 0;
	}
```

- `public static IsDead(Game.Citizens.HealthProblem healthProblem) : System.Boolean`  

```csharp
public static bool IsDead(HealthProblem healthProblem)
	{
		return (healthProblem.m_Flags & HealthProblemFlags.Dead) != 0;
	}
```

- `public static IsHouseholdNeedSupport(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : System.Boolean`  

```csharp
public static bool IsHouseholdNeedSupport(DynamicBuffer<HouseholdCitizen> householdCitizens, ref ComponentLookup<Citizen> citizens, ref ComponentLookup<Student> students)
	{
		bool result = true;
		for (int i = 0; i < householdCitizens.Length; i++)
		{
			Entity citizen = householdCitizens[i].m_Citizen;
			if (citizens[citizen].GetAge() == CitizenAge.Adult && !students.HasComponent(citizen))
			{
				result = false;
				break;
			}
		}
		return result;
	}
```

- `public static IsResident(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Citizens.Citizen& citizen) : System.Boolean`  

```csharp
public static bool IsResident(Entity entity, Citizen citizen, ComponentLookup<HouseholdMember> householdMemberFromEntity, ComponentLookup<MovingAway> movingAwayFromEntity, ComponentLookup<TouristHousehold> touristHouseholdFromEntity, ComponentLookup<CommuterHousehold> commuterHouseholdFromEntity)
	{
		if (!householdMemberFromEntity.TryGetComponent(entity, out var componentData))
		{
			return false;
		}
		if (touristHouseholdFromEntity.HasComponent(componentData.m_Household))
		{
			return false;
		}
		if (commuterHouseholdFromEntity.HasComponent(componentData.m_Household))
		{
			return false;
		}
		if (movingAwayFromEntity.HasComponent(componentData.m_Household))
		{
			return false;
		}
		return (citizen.m_State & (CitizenFlags.MovingAwayReachOC | CitizenFlags.Tourist | CitizenFlags.Commuter)) == 0;
	}
```

- `public static IsResident(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> householdMemberFromEntity, Unity.Entities.ComponentLookup<Game.Agents.MovingAway> movingAwayFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> touristHouseholdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.CommuterHousehold> commuterHouseholdFromEntity) : System.Boolean`  

```csharp
public static bool IsResident(Entity entity, Citizen citizen, ComponentLookup<HouseholdMember> householdMemberFromEntity, ComponentLookup<MovingAway> movingAwayFromEntity, ComponentLookup<TouristHousehold> touristHouseholdFromEntity, ComponentLookup<CommuterHousehold> commuterHouseholdFromEntity)
	{
		if (!householdMemberFromEntity.TryGetComponent(entity, out var componentData))
		{
			return false;
		}
		if (touristHouseholdFromEntity.HasComponent(componentData.m_Household))
		{
			return false;
		}
		if (commuterHouseholdFromEntity.HasComponent(componentData.m_Household))
		{
			return false;
		}
		if (movingAwayFromEntity.HasComponent(componentData.m_Household))
		{
			return false;
		}
		return (citizen.m_State & (CitizenFlags.MovingAwayReachOC | CitizenFlags.Tourist | CitizenFlags.Commuter)) == 0;
	}
```

- `public static IsWorkableCitizen(Unity.Entities.Entity citizenEntity, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_Students, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems) : System.Boolean`  

```csharp
public static bool IsWorkableCitizen(Entity citizenEntity, ref ComponentLookup<Citizen> citizens, ref ComponentLookup<Student> m_Students, ref ComponentLookup<HealthProblem> healthProblems)
	{
		if ((!healthProblems.HasComponent(citizenEntity) || !IsDead(healthProblems[citizenEntity])) && !m_Students.HasComponent(citizenEntity) && (citizens[citizenEntity].m_State & (CitizenFlags.Tourist | CitizenFlags.Commuter)) == 0 && (citizens[citizenEntity].GetAge() == CitizenAge.Teen || citizens[citizenEntity].GetAge() == CitizenAge.Adult))
		{
			return true;
		}
		return false;
	}
```

- `public static TryGetResident(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Game.Citizens.Citizen& citizen) : System.Boolean`  

```csharp
public static bool TryGetResident(Entity entity, ComponentLookup<Citizen> citizenFromEntity, out Citizen citizen)
	{
		if (citizenFromEntity.TryGetComponent(entity, out citizen))
		{
			return (citizen.m_State & (CitizenFlags.MovingAwayReachOC | CitizenFlags.Tourist | CitizenFlags.Commuter)) == 0;
		}
		return false;
	}
```


