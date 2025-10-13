# Game.UI.InGame.CompanyUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CompanyUIUtils
{
    public static Game.UI.InGame.CompanyProfitabilityKey GetProfitabilityKey(System.Int32 profit);
    public static System.Boolean HasCompany(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.Entity& company);
    public static System.Boolean HasCompany(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterFromEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDataFromEntity, Unity.Entities.ComponentLookup`1[[Game.Companies.CompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& companyDataFromEntity, Unity.Entities.Entity& company);
}
```


## Methods

- `public static GetProfitabilityKey(System.Int32 profit) : Game.UI.InGame.CompanyProfitabilityKey`  

```csharp
public static CompanyProfitabilityKey GetProfitabilityKey(int profit)
	{
		if (profit > 128)
		{
			return CompanyProfitabilityKey.Profitable;
		}
		if (profit > 32)
		{
			return CompanyProfitabilityKey.GettingBy;
		}
		if (profit > -64)
		{
			return CompanyProfitabilityKey.BreakingEven;
		}
		if (profit > -182)
		{
			return CompanyProfitabilityKey.LosingMoney;
		}
		return CompanyProfitabilityKey.Bankrupt;
	}
```

- `public static HasCompany(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.Entity& company) : System.Boolean`  

```csharp
public static bool HasCompany(Entity entity, Entity prefab, ref BufferLookup<Renter> renterFromEntity, ref ComponentLookup<BuildingPropertyData> buildingPropertyDataFromEntity, ref ComponentLookup<CompanyData> companyDataFromEntity, out Entity company)
	{
		company = Entity.Null;
		if (renterFromEntity.HasBuffer(entity) && buildingPropertyDataFromEntity.TryGetComponent(prefab, out var componentData) && componentData.CountProperties(AreaType.Commercial) + componentData.CountProperties(AreaType.Industrial) > 0)
		{
			if (renterFromEntity.TryGetBuffer(entity, out var bufferData))
			{
				for (int i = 0; i < bufferData.Length; i++)
				{
					if (companyDataFromEntity.HasComponent(bufferData[i].m_Renter))
					{
						company = bufferData[i].m_Renter;
						break;
					}
				}
			}
			return true;
		}
		return false;
	}
```

- `public static HasCompany(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterFromEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDataFromEntity, Unity.Entities.ComponentLookup`1[[Game.Companies.CompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& companyDataFromEntity, Unity.Entities.Entity& company) : System.Boolean`  

```csharp
public static bool HasCompany(Entity entity, Entity prefab, ref BufferLookup<Renter> renterFromEntity, ref ComponentLookup<BuildingPropertyData> buildingPropertyDataFromEntity, ref ComponentLookup<CompanyData> companyDataFromEntity, out Entity company)
	{
		company = Entity.Null;
		if (renterFromEntity.HasBuffer(entity) && buildingPropertyDataFromEntity.TryGetComponent(prefab, out var componentData) && componentData.CountProperties(AreaType.Commercial) + componentData.CountProperties(AreaType.Industrial) > 0)
		{
			if (renterFromEntity.TryGetBuffer(entity, out var bufferData))
			{
				for (int i = 0; i < bufferData.Length; i++)
				{
					if (companyDataFromEntity.HasComponent(bufferData[i].m_Renter))
					{
						company = bufferData[i].m_Renter;
						break;
					}
				}
			}
			return true;
		}
		return false;
	}
```


