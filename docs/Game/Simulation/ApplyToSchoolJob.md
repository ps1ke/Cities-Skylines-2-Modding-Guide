# Game.Simulation.ApplyToSchoolSystem+ApplyToSchoolJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ApplyToSchoolJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType;
    public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType;
    public Unity.Entities.ComponentTypeHandle<Game.Citizens.Worker> m_WorkerType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas;
    public Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> m_HouseholdMembers;
    public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdDatas;
    public Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources;
    public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
    public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers;
    public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees;
    public Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> m_TouristHouseholds;
    public Unity.Entities.ComponentLookup<Game.Agents.MovingAway> m_MovingAways;
    public Unity.Entities.ComponentLookup<Game.Citizens.SchoolSeekerCooldown> m_SchoolSeekerCooldowns;
    public Game.Common.RandomSeed m_RandomSeed;
    public System.UInt32 m_UpdateFrameIndex;
    public Unity.Entities.Entity m_City;
    public System.UInt32 m_SimulationFrame;
    public Game.Prefabs.EconomyParameterData m_EconomyParameters;
    public Game.Prefabs.EducationParameterData m_EducationParameters;
    public Game.Common.TimeData m_TimeData;
    public System.Boolean m_DebugFastApplySchool;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType`  

```csharp
public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Worker> m_WorkerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Citizens.Worker> m_WorkerType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> m_HouseholdMembers`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.HouseholdMember> m_HouseholdMembers;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdDatas;
```

- `public Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources`  

```csharp
public Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
```

- `public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  

```csharp
public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers;
```

- `public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees`  

```csharp
public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> m_TouristHouseholds`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> m_TouristHouseholds;
```

- `public Unity.Entities.ComponentLookup<Game.Agents.MovingAway> m_MovingAways`  

```csharp
public Unity.Entities.ComponentLookup<Game.Agents.MovingAway> m_MovingAways;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.SchoolSeekerCooldown> m_SchoolSeekerCooldowns`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.SchoolSeekerCooldown> m_SchoolSeekerCooldowns;
```

- `public Game.Common.RandomSeed m_RandomSeed`  

```csharp
public Game.Common.RandomSeed m_RandomSeed;
```

- `public System.UInt32 m_UpdateFrameIndex`  

```csharp
public System.UInt32 m_UpdateFrameIndex;
```

- `public Unity.Entities.Entity m_City`  

```csharp
public Unity.Entities.Entity m_City;
```

- `public System.UInt32 m_SimulationFrame`  

```csharp
public System.UInt32 m_SimulationFrame;
```

- `public Game.Prefabs.EconomyParameterData m_EconomyParameters`  

```csharp
public Game.Prefabs.EconomyParameterData m_EconomyParameters;
```

- `public Game.Prefabs.EducationParameterData m_EducationParameters`  

```csharp
public Game.Prefabs.EducationParameterData m_EducationParameters;
```

- `public Game.Common.TimeData m_TimeData`  

```csharp
public Game.Common.TimeData m_TimeData;
```

- `public System.Boolean m_DebugFastApplySchool`  

```csharp
public System.Boolean m_DebugFastApplySchool;
```

- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
```


## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


