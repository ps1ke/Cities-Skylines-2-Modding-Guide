# Game.Simulation.ApplyToSchoolSystem+ApplyToSchoolJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Worker> m_WorkerType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> m_HouseholdMembers`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdDatas`  
- `public Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  
- `public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  
- `public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> m_TouristHouseholds`  
- `public Unity.Entities.ComponentLookup<Game.Agents.MovingAway> m_MovingAways`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.SchoolSeekerCooldown> m_SchoolSeekerCooldowns`  
- `public Game.Common.RandomSeed m_RandomSeed`  
- `public System.UInt32 m_UpdateFrameIndex`  
- `public Unity.Entities.Entity m_City`  
- `public System.UInt32 m_SimulationFrame`  
- `public Game.Prefabs.EconomyParameterData m_EconomyParameters`  
- `public Game.Prefabs.EducationParameterData m_EducationParameters`  
- `public Game.Common.TimeData m_TimeData`  
- `public System.Boolean m_DebugFastApplySchool`  
- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

