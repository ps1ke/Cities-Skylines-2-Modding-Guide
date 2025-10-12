# Game.Simulation.CityServiceUpkeepSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  
- `private Unity.Entities.EntityQuery m_UpkeepGroup`  
- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  
- `private Game.Simulation.CityServiceUpkeepSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public CityServiceUpkeepSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static CalculateUpkeep(System.Int32 amount, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity budgetEntity, Unity.Entities.EntityManager entityManager) : System.Int32`  
- `public static GetResourceAvailability(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> upkeeps, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Collections.NativeArray<System.Int32> storageTargets) : System.Byte`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static GetUpkeepModifierData(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> upkeepModifierList, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabs, Unity.Entities.BufferLookup<Game.Prefabs.UpkeepModifierData> upkeepModifiers, Unity.Entities.Entity entity) : System.Void`  
- `public static GetUpkeepOfEmployeeWage(Unity.Entities.BufferLookup<Game.Companies.Employee> employeeBufs, Unity.Entities.Entity entity, Game.Prefabs.EconomyParameterData economyParameterData, System.Boolean mainBuildingDisabled) : System.Int32`  
- `public static GetUpkeepWithUsageScale(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> totalUpkeepDatas, Unity.Entities.BufferLookup<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgradeBufs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Buildings.ServiceUsage> serviceUsages, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, System.Boolean mainBuildingDisabled) : System.Void`  
- `public static IsMaterialResource(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.ResourceStack upkeep) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CityServiceUpkeepSystem+CityServiceUpkeepJob`  
- `Game.Simulation.CityServiceUpkeepSystem+TypeHandle`  

