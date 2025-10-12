# Game.Simulation.AdjustWaterConsumptionSystem+AdjustWaterConsumptionJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType`  
- `public Unity.Entities.ComponentTypeHandle<Game.City.CityServiceUpkeep> m_CityServiceType`  
- `public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_UpgradeType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeBuildingConnection> m_BuildingConnectionType`  
- `public Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Park> m_ParkType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.StorageProperty> m_StoragePropertyType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.WaterConsumer> m_ConsumerType`  
- `public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_EfficiencyType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ConsumptionData> m_ServiceConsumption`  
- `public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees`  
- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens`  
- `public Unity.Entities.BufferLookup<Game.Companies.Employee> m_Employees`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens`  
- `public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> m_FlowEdges`  
- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges`  
- `public Game.Prefabs.ServiceFeeParameterData m_FeeParameters`  
- `public Game.Prefabs.BuildingEfficiencyParameterData m_EfficiencyParameters`  
- `public Game.Common.RandomSeed m_RandomSeed`  
- `public Unity.Entities.Entity m_City`  
- `public System.UInt32 m_UpdateFrameIndex`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

