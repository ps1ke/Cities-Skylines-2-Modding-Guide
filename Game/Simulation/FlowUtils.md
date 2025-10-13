# Game.Simulation.FlowUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class FlowUtils
{
    public static System.Int32 ConsumeFromTotal(System.Int32 demand, System.Int32& totalSupply, System.Int32& totalDemand);
    public static System.Single GetRenterConsumptionMultiplier(Unity.Entities.Entity prefab, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renterBuffer, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas);
}
```


## Methods

- `public static ConsumeFromTotal(System.Int32 demand, System.Int32& totalSupply, System.Int32& totalDemand) : System.Int32`  

```csharp
public static int ConsumeFromTotal(int demand, ref int totalSupply, ref int totalDemand)
	{
		int num = 0;
		if (demand > 0)
		{
			int lowerBound = totalSupply - (totalDemand - demand);
			int upperBound = totalSupply;
			int num2 = totalDemand * 100 / demand;
			num = math.clamp(totalSupply * 100 / num2, lowerBound, upperBound);
			totalSupply -= num;
			totalDemand -= demand;
		}
		return num;
	}
```

- `public static GetRenterConsumptionMultiplier(Unity.Entities.Entity prefab, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renterBuffer, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas) : System.Single`  

```csharp
public static float GetRenterConsumptionMultiplier(Entity prefab, DynamicBuffer<Renter> renterBuffer, ref BufferLookup<HouseholdCitizen> householdCitizens, ref BufferLookup<Employee> employees, ref ComponentLookup<Citizen> citizens, ref ComponentLookup<SpawnableBuildingData> spawnableDatas)
	{
		int num = 0;
		float num2 = 0f;
		foreach (Renter item in renterBuffer)
		{
			if (householdCitizens.TryGetBuffer(item, out var bufferData))
			{
				foreach (HouseholdCitizen item2 in bufferData)
				{
					if (citizens.TryGetComponent(item2.m_Citizen, out var componentData))
					{
						num2 += (float)componentData.GetEducationLevel();
						num++;
					}
				}
			}
			else
			{
				if (!employees.TryGetBuffer(item, out var bufferData2))
				{
					continue;
				}
				foreach (Employee item3 in bufferData2)
				{
					if (citizens.TryGetComponent(item3.m_Worker, out var componentData2))
					{
						num2 += (float)componentData2.GetEducationLevel();
						num++;
					}
				}
			}
		}
		if (num != 0)
		{
			SpawnableBuildingData componentData3;
			float num3 = (spawnableDatas.TryGetComponent(prefab, out componentData3) ? ((float)(int)componentData3.m_Level) : 5f);
			return 5f * (float)num / (num3 + 0.5f * (num2 / (float)num));
		}
		return 0f;
	}
```


