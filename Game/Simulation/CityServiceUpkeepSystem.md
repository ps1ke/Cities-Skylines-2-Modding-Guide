# Game.Simulation.CityServiceUpkeepSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityServiceUpkeepSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Unity.Entities.EntityQuery m_UpkeepGroup;
    private Unity.Entities.EntityQuery m_BudgetDataQuery;
    private Game.Simulation.CityServiceUpkeepSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kUpdatesPerDay;

    public CityServiceUpkeepSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 CalculateUpkeep(System.Int32 amount, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity budgetEntity, Unity.Entities.EntityManager entityManager);
    public static System.Byte GetResourceAvailability(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> upkeeps, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Collections.NativeArray<System.Int32> storageTargets);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Void GetUpkeepModifierData(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> upkeepModifierList, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabs, Unity.Entities.BufferLookup<Game.Prefabs.UpkeepModifierData> upkeepModifiers, Unity.Entities.Entity entity);
    public static System.Int32 GetUpkeepOfEmployeeWage(Unity.Entities.BufferLookup<Game.Companies.Employee> employeeBufs, Unity.Entities.Entity entity, Game.Prefabs.EconomyParameterData economyParameterData, System.Boolean mainBuildingDisabled);
    public static System.Void GetUpkeepWithUsageScale(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> totalUpkeepDatas, Unity.Entities.BufferLookup<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgradeBufs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Buildings.ServiceUsage> serviceUsages, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, System.Boolean mainBuildingDisabled);
    public static System.Boolean IsMaterialResource(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.ResourceStack upkeep);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Unity.Entities.EntityQuery m_UpkeepGroup`  

```csharp
private Unity.Entities.EntityQuery m_UpkeepGroup;
```

- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_BudgetDataQuery;
```

- `private Game.Simulation.CityServiceUpkeepSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CityServiceUpkeepSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kUpdatesPerDay`  

```csharp
private static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public CityServiceUpkeepSystem()`  

```csharp
public CityServiceUpkeepSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static CalculateUpkeep(System.Int32 amount, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity budgetEntity, Unity.Entities.EntityManager entityManager) : System.Int32`  

```csharp
public static System.Int32 CalculateUpkeep(System.Int32 amount, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity budgetEntity, Unity.Entities.EntityManager entityManager);
```

- `public static GetResourceAvailability(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> upkeeps, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Collections.NativeArray<System.Int32> storageTargets) : System.Byte`  

```csharp
public static System.Byte GetResourceAvailability(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> upkeeps, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Collections.NativeArray<System.Int32> storageTargets);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static GetUpkeepModifierData(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> upkeepModifierList, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabs, Unity.Entities.BufferLookup<Game.Prefabs.UpkeepModifierData> upkeepModifiers, Unity.Entities.Entity entity) : System.Void`  

```csharp
public static System.Void GetUpkeepModifierData(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> upkeepModifierList, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabs, Unity.Entities.BufferLookup<Game.Prefabs.UpkeepModifierData> upkeepModifiers, Unity.Entities.Entity entity);
```

- `public static GetUpkeepOfEmployeeWage(Unity.Entities.BufferLookup<Game.Companies.Employee> employeeBufs, Unity.Entities.Entity entity, Game.Prefabs.EconomyParameterData economyParameterData, System.Boolean mainBuildingDisabled) : System.Int32`  

```csharp
public static System.Int32 GetUpkeepOfEmployeeWage(Unity.Entities.BufferLookup<Game.Companies.Employee> employeeBufs, Unity.Entities.Entity entity, Game.Prefabs.EconomyParameterData economyParameterData, System.Boolean mainBuildingDisabled);
```

- `public static GetUpkeepWithUsageScale(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> totalUpkeepDatas, Unity.Entities.BufferLookup<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgradeBufs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Buildings.ServiceUsage> serviceUsages, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, System.Boolean mainBuildingDisabled) : System.Void`  

```csharp
public static System.Void GetUpkeepWithUsageScale(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> totalUpkeepDatas, Unity.Entities.BufferLookup<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgradeBufs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Buildings.ServiceUsage> serviceUsages, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, System.Boolean mainBuildingDisabled);
```

- `public static IsMaterialResource(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.ResourceStack upkeep) : System.Boolean`  

```csharp
public static System.Boolean IsMaterialResource(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.ResourceStack upkeep);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.CityServiceUpkeepSystem+CityServiceUpkeepJob`  
- `Game.Simulation.CityServiceUpkeepSystem+TypeHandle`  

