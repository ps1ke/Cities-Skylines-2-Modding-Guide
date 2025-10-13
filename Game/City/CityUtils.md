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
public static System.Void ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.City.CityModifierType type);
```

- `public static CheckOption(Game.City.City city, Game.City.CityOption option) : System.Boolean`  

```csharp
public static System.Boolean CheckOption(Game.City.City city, Game.City.CityOption option);
```

- `public static GetCityServiceWorkplaceMaxWorkers(Unity.Entities.Entity ownerEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Common.Deleted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deleteds, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SchoolData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& schoolDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& studentBufs) : System.Int32`  

```csharp
public static System.Int32 GetCityServiceWorkplaceMaxWorkers(Unity.Entities.Entity ownerEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Common.Deleted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deleteds, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SchoolData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& schoolDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& studentBufs);
```

- `public static GetModifier(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.City.CityModifierType type) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetModifier(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.City.CityModifierType type);
```

- `public static HasOption(Game.Prefabs.CityOptionData optionData, Game.City.CityOption option) : System.Boolean`  

```csharp
public static System.Boolean HasOption(Game.Prefabs.CityOptionData optionData, Game.City.CityOption option);
```


