# Game.Simulation.BuildingUpkeepSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingUpkeepSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Prefabs.ZoneBuiltRequirementSystem m_ZoneBuiltRequirementSystemSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.BuildingUpkeepSystem+UpkeepPayment> m_UpkeepExpenseQueue;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LevelupQueue;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LeveldownQueue;
    private Unity.Entities.EntityQuery m_BuildingPrefabGroup;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Unity.Entities.EntityQuery m_BuildingGroup;
    public System.Boolean debugFastLeveling;
    private Game.Simulation.BuildingUpkeepSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kMaterialUpkeep;

    public BuildingUpkeepSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void DebugLevelDown(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas);
    public System.Void DebugLevelUp(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas);
    public static System.Single GetHeatingMultiplier(System.Single temperature);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Prefabs.ZoneBuiltRequirementSystem m_ZoneBuiltRequirementSystemSystem`  

```csharp
private Game.Prefabs.ZoneBuiltRequirementSystem m_ZoneBuiltRequirementSystemSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
```

- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingUpkeepSystem+UpkeepPayment> m_UpkeepExpenseQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.BuildingUpkeepSystem+UpkeepPayment> m_UpkeepExpenseQueue;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LevelupQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LevelupQueue;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LeveldownQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LeveldownQueue;
```

- `private Unity.Entities.EntityQuery m_BuildingPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `public System.Boolean debugFastLeveling`  

```csharp
public System.Boolean debugFastLeveling;
```

- `private Game.Simulation.BuildingUpkeepSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BuildingUpkeepSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kMaterialUpkeep`  

```csharp
public static readonly System.Int32 kMaterialUpkeep;
```


## Constructors

- `public BuildingUpkeepSystem()`  

```csharp
public BuildingUpkeepSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public DebugLevelDown(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas) : System.Void`  

```csharp
public System.Void DebugLevelDown(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas);
```

- `public DebugLevelUp(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas) : System.Void`  

```csharp
public System.Void DebugLevelUp(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas);
```

- `public static GetHeatingMultiplier(System.Single temperature) : System.Single`  

```csharp
public static System.Single GetHeatingMultiplier(System.Single temperature);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.BuildingUpkeepSystem+UpkeepPayment`  
- `Game.Simulation.BuildingUpkeepSystem+BuildingUpkeepJob`  
- `Game.Simulation.BuildingUpkeepSystem+UpkeepPaymentJob`  
- `Game.Simulation.BuildingUpkeepSystem+LeveldownJob`  
- `Game.Simulation.BuildingUpkeepSystem+LevelupJob`  
- `Game.Simulation.BuildingUpkeepSystem+TypeHandle`  

