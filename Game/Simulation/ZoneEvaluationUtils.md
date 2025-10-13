# Game.Simulation.ZoneEvaluationUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ZoneEvaluationUtils
{
    public ZoneEvaluationUtils();

    public static System.Single GetCommercialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Boolean lodging);
    private static System.Single GetFactor(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Net.AvailableResource resource);
    public static System.Void GetFactors(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> results, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single pollution, System.Single landvalue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas);
    public static System.Single GetResidentialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Single pollution);
    public static System.Single GetScore(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Boolean storage, Unity.Collections.NativeArray<System.Int32> resourceDemands, Game.Prefabs.BuildingPropertyData propertyData, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
    private static System.Single GetStorageScore(Game.Economy.Resource resource, System.Single price, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos);
    private static System.Single GetTransportScore(Game.Economy.Resource allowedManufactured, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single curvePos, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
}
```


## Constructors

- `public ZoneEvaluationUtils()`  

```csharp
public ZoneEvaluationUtils();
```


## Methods

- `public static GetCommercialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Boolean lodging) : System.Single`  

```csharp
public static float GetCommercialScore(DynamicBuffer<ResourceAvailability> availabilities, float curvePos, ref ZonePreferenceData preferences, float landValue, bool lodging)
	{
		float num = 0f;
		float factor = GetFactor(availabilities, curvePos, AvailableResource.UneducatedCitizens);
		float factor2 = GetFactor(availabilities, curvePos, AvailableResource.EducatedCitizens);
		float factor3 = GetFactor(availabilities, curvePos, AvailableResource.Workplaces);
		float factor4 = GetFactor(availabilities, curvePos, AvailableResource.Services);
		num += math.max(preferences.m_CommercialSignificanceConsumers * (2f - math.lerp(factor, factor2, 0.67f)), preferences.m_CommercialSignificanceWorkplaces * (2f - factor3));
		num += preferences.m_CommercialSignificanceCompetitors * (-0.4f + factor4);
		num += preferences.m_CommercialSignificanceLandValue * (landValue - preferences.m_CommercialNeutralLandValue);
		return 555f + num;
	}
```

- `private static GetFactor(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Net.AvailableResource resource) : System.Single`  

```csharp
private static float GetFactor(DynamicBuffer<ResourceAvailability> availabilities, float curvePos, AvailableResource resource)
	{
		return math.min(20f, 0.2f / NetUtils.GetAvailability(availabilities, resource, curvePos));
	}
```

- `public static GetFactors(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> results, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single pollution, System.Single landvalue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas) : System.Void`  

```csharp
public static void GetFactors(AreaType areaType, bool office, DynamicBuffer<ResourceAvailability> availabilities, float curvePos, ref ZonePreferenceData preferences, NativeList<ZoningEvaluationResult> results, NativeArray<int> resourceDemands, float pollution, float landvalue, DynamicBuffer<ProcessEstimate> estimates, NativeList<IndustrialProcessData> processes, ResourcePrefabs resourcePrefabs, ComponentLookup<ResourceData> resourceDatas)
	{
		switch (areaType)
		{
		case AreaType.Residential:
		{
			float factor2 = GetFactor(availabilities, curvePos, AvailableResource.Services);
			float factor4 = GetFactor(availabilities, curvePos, AvailableResource.Workplaces);
			ZoningEvaluationResult value = new ZoningEvaluationResult
			{
				m_Factor = ZoningEvaluationFactor.Services,
				m_Score = 20f * preferences.m_ResidentialSignificanceServices * (0.2f - factor2)
			};
			results.Add(in value);
			value = new ZoningEvaluationResult
			{
				m_Factor = ZoningEvaluationFactor.Workplaces,
				m_Score = 20f * preferences.m_ResidentialSignificanceWorkplaces * (0.2f - factor4)
			};
			results.Add(in value);
			value = new ZoningEvaluationResult
			{
				m_Factor = ZoningEvaluationFactor.Pollution,
				m_Score = 20f + preferences.m_ResidentialSignificancePollution * pollution
			};
			results.Add(in value);
			value = new ZoningEvaluationResult
			{
				m_Factor = ZoningEvaluationFactor.LandValue,
				m_Score = preferences.m_ResidentialSignificanceLandValue * (landvalue - preferences.m_ResidentialNeutralLandValue)
			};
			results.Add(in value);
			break;
		}
		case AreaType.Commercial:
		{
			float factor3 = GetFactor(availabilities, curvePos, AvailableResource.UneducatedCitizens);
			float factor = GetFactor(availabilities, curvePos, AvailableResource.EducatedCitizens);
			float factor4 = GetFactor(availabilities, curvePos, AvailableResource.Workplaces);
			ZoningEvaluationResult value = new ZoningEvaluationResult
			{
				m_Factor = ZoningEvaluationFactor.Customers,
				m_Score = math.max(preferences.m_CommercialSignificanceConsumers * (2f - math.lerp(factor3, factor, 0.67f)), preferences.m_CommercialSignificanceWorkplaces * (2f - factor4))
			};
			results.Add(in value);
			float factor2 = GetFactor(availabilities, curvePos, AvailableResource.Services);
			value = new ZoningEvaluationResult
			{
				m_Factor = ZoningEvaluationFactor.Competitors,
				m_Score = preferences.m_CommercialSignificanceCompetitors * (-0.4f + factor2)
			};
			results.Add(in value);
			value = new ZoningEvaluationResult
			{
				m_Factor = ZoningEvaluationFactor.LandValue,
				m_Score = preferences.m_CommercialSignificanceLandValue * (landvalue - preferences.m_CommercialNeutralLandValue)
			};
			results.Add(in value);
			break;
		}
		case AreaType.Industrial:
			if (!office)
			{
				ZoningEvaluationResult value = new ZoningEvaluationResult
				{
					m_Factor = ZoningEvaluationFactor.Inputs,
					m_Score = preferences.m_IndustrialSignificanceInput * GetTransportScore(Resource.All, processes, availabilities, resourceDemands, curvePos, resourcePrefabs, ref resourceDatas)
				};
				results.Add(in value);
				value = new ZoningEvaluationResult
				{
					m_Factor = ZoningEvaluationFactor.LandValue,
					m_Score = preferences.m_IndustrialSignificanceLandValue * (landvalue - preferences.m_IndustrialNeutralLandValue)
				};
				results.Add(in value);
			}
			else
			{
				float factor = GetFactor(availabilities, curvePos, AvailableResource.EducatedCitizens);
				float factor2 = GetFactor(availabilities, curvePos, AvailableResource.Services);
				ZoningEvaluationResult value = new ZoningEvaluationResult
				{
					m_Factor = ZoningEvaluationFactor.Employees,
					m_Score = preferences.m_OfficeSignificanceEmployees * (0.2f - factor)
				};
				results.Add(in value);
				value = new ZoningEvaluationResult
				{
					m_Factor = ZoningEvaluationFactor.Services,
					m_Score = preferences.m_OfficeSignificanceServices * (0.2f - factor2)
				};
				results.Add(in value);
			}
			break;
		}
	}
```

- `public static GetResidentialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Single pollution) : System.Single`  

```csharp
public static float GetResidentialScore(DynamicBuffer<ResourceAvailability> availabilities, float curvePos, ref ZonePreferenceData preferences, float landValue, float pollution)
	{
		float num = (0f - preferences.m_ResidentialSignificanceServices) / math.max(0.1f, NetUtils.GetAvailability(availabilities, AvailableResource.Services, curvePos)) - preferences.m_ResidentialSignificanceWorkplaces / math.max(0.1f, NetUtils.GetAvailability(availabilities, AvailableResource.Workplaces, curvePos));
		num += preferences.m_ResidentialSignificancePollution * pollution;
		num += preferences.m_ResidentialSignificanceLandValue * (landValue - preferences.m_ResidentialNeutralLandValue);
		return 555f + num;
	}
```

- `public static GetScore(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Boolean storage, Unity.Collections.NativeArray<System.Int32> resourceDemands, Game.Prefabs.BuildingPropertyData propertyData, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static float GetScore(AreaType areaType, bool office, DynamicBuffer<ResourceAvailability> availabilities, float curvePos, ref ZonePreferenceData preferences, bool storage, NativeArray<int> resourceDemands, BuildingPropertyData propertyData, float pollution, float landValue, DynamicBuffer<ProcessEstimate> estimates, NativeList<IndustrialProcessData> processes, ResourcePrefabs resourcePrefabs, ref ComponentLookup<ResourceData> resourceDatas)
	{
		switch (areaType)
		{
		case AreaType.Residential:
			return GetResidentialScore(availabilities, curvePos, ref preferences, landValue, pollution);
		case AreaType.Commercial:
			return 0.9f * GetCommercialScore(availabilities, curvePos, ref preferences, landValue, lodging: false) + 0.1f * GetCommercialScore(availabilities, curvePos, ref preferences, landValue, lodging: true);
		case AreaType.Industrial:
			if (storage)
			{
				Resource allowedStored = propertyData.m_AllowedStored;
				ResourceIterator iterator = ResourceIterator.GetIterator();
				float num = float.PositiveInfinity;
				while (iterator.Next())
				{
					if ((allowedStored & iterator.resource) != Resource.NoResource && resourceDemands[EconomyUtils.GetResourceIndex(iterator.resource)] != 0)
					{
						EconomyUtils.GetWeight(iterator.resource, resourcePrefabs, ref resourceDatas);
						float marketPrice = EconomyUtils.GetMarketPrice(iterator.resource, resourcePrefabs, ref resourceDatas);
						num = math.min(num, GetStorageScore(iterator.resource, marketPrice, availabilities, curvePos));
						num = math.min(num, 0.05f / math.max(0.1f, NetUtils.GetAvailability(availabilities, EconomyUtils.GetAvailableResourceSupply(iterator.resource), curvePos)));
					}
				}
				return math.max(0f, 555f - 10f * num);
			}
			if (office)
			{
				float factor = GetFactor(availabilities, curvePos, AvailableResource.EducatedCitizens);
				float factor2 = GetFactor(availabilities, curvePos, AvailableResource.Services);
				return 555f + preferences.m_OfficeSignificanceEmployees * (0.25f - 5f * factor) + preferences.m_OfficeSignificanceServices * (0.25f - 2f * factor2);
			}
			return 555f + preferences.m_IndustrialSignificanceInput * GetTransportScore(propertyData.m_AllowedManufactured, processes, availabilities, resourceDemands, curvePos, resourcePrefabs, ref resourceDatas) + preferences.m_IndustrialSignificanceLandValue * (landValue - preferences.m_IndustrialNeutralLandValue) - 0.5f * landValue;
		default:
			return 0f;
		}
	}
```

- `private static GetStorageScore(Game.Economy.Resource resource, System.Single price, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos) : System.Single`  

```csharp
private static float GetStorageScore(Resource resource, float price, DynamicBuffer<ResourceAvailability> availabilities, float curvePos)
	{
		float num = 1f / (price * math.max(0.1f, NetUtils.GetAvailability(availabilities, EconomyUtils.GetAvailableResourceSupply(resource), curvePos)));
		float num2 = 0f;
		int num3 = 0;
		ResourceIterator iterator = ResourceIterator.GetIterator();
		while (iterator.Next())
		{
			if (EconomyUtils.IsProducedFrom(iterator.resource, resource) && EconomyUtils.GetAvailableResourceSupply(iterator.resource) != AvailableResource.Count)
			{
				num2 += 1f / (price * math.max(0.1f, NetUtils.GetAvailability(availabilities, EconomyUtils.GetAvailableResourceSupply(iterator.resource), curvePos)));
				num3++;
			}
		}
		if (num3 == 0)
		{
			num2 = 1f / (price * math.max(0.1f, NetUtils.GetAvailability(availabilities, AvailableResource.ConvenienceFoodStore, curvePos)));
			num3 = 1;
		}
		return num + num2 / (float)num3;
	}
```

- `private static GetTransportScore(Game.Economy.Resource allowedManufactured, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single curvePos, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
private static float GetTransportScore(Resource allowedManufactured, NativeList<IndustrialProcessData> processes, DynamicBuffer<ResourceAvailability> availabilities, NativeArray<int> resourceDemands, float curvePos, ResourcePrefabs resourcePrefabs, ref ComponentLookup<ResourceData> resourceDatas)
	{
		float num = 0f;
		float num2 = 0f;
		ResourceIterator iterator = ResourceIterator.GetIterator();
		while (iterator.Next())
		{
			if ((allowedManufactured & iterator.resource) == Resource.NoResource)
			{
				continue;
			}
			ResourceIterator iterator2 = ResourceIterator.GetIterator();
			while (iterator2.Next())
			{
				if (!EconomyUtils.IsProducedFrom(iterator.resource, iterator2.resource) || EconomyUtils.GetAvailableResourceSupply(iterator2.resource) == AvailableResource.Count)
				{
					continue;
				}
				EconomyUtils.GetResourceIndex(iterator2.resource);
				for (int i = 0; i < processes.Length; i++)
				{
					IndustrialProcessData industrialProcessData = processes[i];
					if (industrialProcessData.m_Output.m_Resource != iterator.resource || industrialProcessData.m_Input1.m_Resource == industrialProcessData.m_Output.m_Resource)
					{
						continue;
					}
					int num3 = Mathf.Max((industrialProcessData.m_Input1.m_Resource == iterator2.resource) ? industrialProcessData.m_Input1.m_Amount : 0, (industrialProcessData.m_Input2.m_Resource == iterator2.resource) ? industrialProcessData.m_Input2.m_Amount : 0);
					int num4 = resourceDemands[EconomyUtils.GetResourceIndex(iterator.resource)] + 1;
					float num5 = math.max(0.1f, NetUtils.GetAvailability(availabilities, EconomyUtils.GetAvailableResourceSupply(iterator2.resource), curvePos));
					if (num3 > 0 && num4 > 0 && num5 > 0f)
					{
						float num6 = (float)num3 / ((float)industrialProcessData.m_Output.m_Amount * num5);
						float num7 = math.min(5f, EconomyUtils.GetMarketPrice(iterator2.resource, resourcePrefabs, ref resourceDatas));
						if (num6 < 0.3f * num7)
						{
							num += (float)num4 * (0.3f * num7 - num6);
							num2 += (float)num4 * 0.3f * num7;
						}
					}
				}
			}
		}
		if (num2 > 0f)
		{
			return num / num2 - 0.5f;
		}
		return 0f;
	}
```


## Nested types

- `Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor`  
- `Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult`  

