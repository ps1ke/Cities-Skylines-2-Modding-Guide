# Game.Simulation.BuildingUpkeepSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Prefabs.ZoneBuiltRequirementSystem m_ZoneBuiltRequirementSystemSystem`  
- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  
- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  
- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  
- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingUpkeepSystem+UpkeepPayment> m_UpkeepExpenseQueue`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LevelupQueue`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LeveldownQueue`  
- `private Unity.Entities.EntityQuery m_BuildingPrefabGroup`  
- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  
- `private Unity.Entities.EntityQuery m_BuildingGroup`  
- `public System.Boolean debugFastLeveling`  
- `private Game.Simulation.BuildingUpkeepSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static readonly System.Int32 kMaterialUpkeep`  

## Constructors

- `public BuildingUpkeepSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public DebugLevelDown(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas) : System.Void`  
- `public DebugLevelUp(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas) : System.Void`  
- `public static GetHeatingMultiplier(System.Single temperature) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.BuildingUpkeepSystem+UpkeepPayment`  
- `Game.Simulation.BuildingUpkeepSystem+BuildingUpkeepJob`  
- `Game.Simulation.BuildingUpkeepSystem+UpkeepPaymentJob`  
- `Game.Simulation.BuildingUpkeepSystem+LeveldownJob`  
- `Game.Simulation.BuildingUpkeepSystem+LevelupJob`  
- `Game.Simulation.BuildingUpkeepSystem+TypeHandle`  

