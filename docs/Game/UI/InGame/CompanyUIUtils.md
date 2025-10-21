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
public static Game.UI.InGame.CompanyProfitabilityKey GetProfitabilityKey(System.Int32 profit);
```

- `public static HasCompany(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.Entity& company) : System.Boolean`  

```csharp
public static System.Boolean HasCompany(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.Entity& company);
```

- `public static HasCompany(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterFromEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDataFromEntity, Unity.Entities.ComponentLookup`1[[Game.Companies.CompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& companyDataFromEntity, Unity.Entities.Entity& company) : System.Boolean`  

```csharp
public static System.Boolean HasCompany(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterFromEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDataFromEntity, Unity.Entities.ComponentLookup`1[[Game.Companies.CompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& companyDataFromEntity, Unity.Entities.Entity& company);
```


