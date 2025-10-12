# Game.Simulation.SewageOutletAISystem+OutletTickJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeBuildingConnection> m_BuildingConnectionType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `public Unity.Entities.BufferTypeHandle<Game.Objects.SubObject> m_SubObjectType`  
- `public Unity.Entities.BufferTypeHandle<Game.Notifications.IconElement> m_IconElementType`  
- `public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_EfficiencyType`  
- `public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.SewageOutlet> m_SewageOutletType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SewageOutletData> m_OutletDatas`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SewageOutletData> m_SewageOutletDatas`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  
- `public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> m_FlowEdges`  
- `public Unity.Entities.ComponentLookup<Game.Simulation.WaterSourceData> m_WaterSources`  
- `public Game.Notifications.IconCommandBuffer m_IconCommandBuffer`  
- `public Game.Prefabs.WaterPipeParameterData m_Parameters`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private HasNotification(Unity.Entities.DynamicBuffer<Game.Notifications.IconElement> iconElements, Unity.Entities.Entity notificationPrefab) : System.Boolean`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private UpdateNotification(Unity.Entities.Entity entity, Unity.Entities.Entity notificationPrefab, System.Boolean enabled, Unity.Entities.DynamicBuffer<Game.Notifications.IconElement> iconElements) : System.Void`  

