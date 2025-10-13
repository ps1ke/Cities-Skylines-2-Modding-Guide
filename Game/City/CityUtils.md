# Game.City.CityUtils

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CityUtils
{
    public static System.Void ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.City.CityModifierType type);
    public static System.Boolean CheckOption(Game.City.City city, Game.City.CityOption option);
    public static System.Int32 GetCityServiceWorkplaceMaxWorkers(Unity.Entities.Entity ownerEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Common.Deleted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deleteds, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SchoolData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& schoolDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& studentBufs);
    public static Unity.Mathematics.float2 GetModifier(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.City.CityModifierType type);
    public static System.Boolean HasOption(Game.Prefabs.CityOptionData optionData, Game.City.CityOption option);
}
```


## Methods

- `public static ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.City.CityModifierType type) : System.Void`  

```csharp
public static void ApplyModifier(ref float value, DynamicBuffer<CityModifier> modifiers, CityModifierType type)
	{
		if (modifiers.Length > (int)type)
		{
			float2 delta = modifiers[(int)type].m_Delta;
			value += delta.x;
			value += value * delta.y;
		}
	}
```

- `public static CheckOption(Game.City.City city, Game.City.CityOption option) : System.Boolean`  

```csharp
public static bool CheckOption(City city, CityOption option)
	{
		return (city.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```

- `public static GetCityServiceWorkplaceMaxWorkers(Unity.Entities.Entity ownerEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Common.Deleted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deleteds, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SchoolData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& schoolDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& studentBufs) : System.Int32`  

```csharp
public static int GetCityServiceWorkplaceMaxWorkers(Entity ownerEntity, ref ComponentLookup<PrefabRef> prefabRefs, ref BufferLookup<InstalledUpgrade> installedUpgrades, ref ComponentLookup<Deleted> deleteds, ref ComponentLookup<WorkplaceData> workplaceDatas, ref ComponentLookup<SchoolData> schoolDatas, ref BufferLookup<Student> studentBufs)
	{
		int result = 0;
		if (deleteds.HasComponent(ownerEntity))
		{
			return result;
		}
		Entity entity = prefabRefs[ownerEntity];
		if (!workplaceDatas.HasComponent(entity))
		{
			return result;
		}
		result = workplaceDatas[entity].m_MaxWorkers;
		if (!installedUpgrades.HasBuffer(ownerEntity))
		{
			return result;
		}
		int num = ((workplaceDatas[entity].m_MinimumWorkersLimit == 0) ? result : workplaceDatas[entity].m_MinimumWorkersLimit);
		foreach (InstalledUpgrade item in installedUpgrades[ownerEntity])
		{
			if (prefabRefs.HasComponent(item.m_Upgrade) && !deleteds.HasComponent(item.m_Upgrade))
			{
				Entity entity2 = prefabRefs[item.m_Upgrade];
				if (workplaceDatas.HasComponent(entity2))
				{
					num += workplaceDatas[entity2].m_MinimumWorkersLimit;
					result += workplaceDatas[entity2].m_MaxWorkers;
				}
			}
		}
		if (schoolDatas.HasComponent(entity))
		{
			int studentCapacity = schoolDatas[entity].m_StudentCapacity;
			int length = studentBufs[ownerEntity].Length;
			result = math.max(num, (int)Mathf.Lerp(0f, result, 1f * (float)length / (float)studentCapacity));
		}
		return result;
	}
```

- `public static GetModifier(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.City.CityModifierType type) : Unity.Mathematics.float2`  

```csharp
public static float2 GetModifier(DynamicBuffer<CityModifier> modifiers, CityModifierType type)
	{
		if (modifiers.Length > (int)type)
		{
			return modifiers[(int)type].m_Delta;
		}
		return default(float2);
	}
```

- `public static HasOption(Game.Prefabs.CityOptionData optionData, Game.City.CityOption option) : System.Boolean`  

```csharp
public static bool HasOption(CityOptionData optionData, CityOption option)
	{
		return (optionData.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```


