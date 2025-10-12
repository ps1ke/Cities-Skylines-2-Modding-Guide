# Game.Simulation.GraduationSystem+GraduationJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Student> m_StudentType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_Purposes`  
- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  
- `public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencies`  
- `public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees`  
- `public Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> m_TriggerBuffer`  
- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  
- `public Game.Prefabs.EconomyParameterData m_EconomyParameters`  
- `public Game.Common.TimeData m_TimeData`  
- `public Game.Common.RandomSeed m_RandomSeed`  
- `public System.UInt32 m_SimulationFrame`  
- `public Unity.Entities.Entity m_City`  
- `public System.UInt32 m_UpdateFrameIndex`  
- `public System.Int32 m_DebugFastGraduationLevel`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private LeaveSchool(System.Int32 chunkIndex, Unity.Entities.Entity entity, Unity.Entities.Entity school) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

