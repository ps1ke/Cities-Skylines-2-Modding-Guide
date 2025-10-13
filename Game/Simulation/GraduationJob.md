# Game.Simulation.GraduationSystem+GraduationJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct GraduationJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType;
    public Unity.Entities.ComponentTypeHandle<Game.Citizens.Student> m_StudentType;
    public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas;
    public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_Purposes;
    public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
    public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers;
    public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencies;
    public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees;
    public Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> m_TriggerBuffer;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
    public Game.Prefabs.EconomyParameterData m_EconomyParameters;
    public Game.Common.TimeData m_TimeData;
    public Game.Common.RandomSeed m_RandomSeed;
    public System.UInt32 m_SimulationFrame;
    public Unity.Entities.Entity m_City;
    public System.UInt32 m_UpdateFrameIndex;
    public System.Int32 m_DebugFastGraduationLevel;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void LeaveSchool(System.Int32 chunkIndex, Unity.Entities.Entity entity, Unity.Entities.Entity school);
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

- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Student> m_StudentType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Citizens.Student> m_StudentType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_Purposes`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_Purposes;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
```

- `public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  

```csharp
public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencies`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencies;
```

- `public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees`  

```csharp
public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees;
```

- `public Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> m_TriggerBuffer`  

```csharp
public Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> m_TriggerBuffer;
```

- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
```

- `public Game.Prefabs.EconomyParameterData m_EconomyParameters`  

```csharp
public Game.Prefabs.EconomyParameterData m_EconomyParameters;
```

- `public Game.Common.TimeData m_TimeData`  

```csharp
public Game.Common.TimeData m_TimeData;
```

- `public Game.Common.RandomSeed m_RandomSeed`  

```csharp
public Game.Common.RandomSeed m_RandomSeed;
```

- `public System.UInt32 m_SimulationFrame`  

```csharp
public System.UInt32 m_SimulationFrame;
```

- `public Unity.Entities.Entity m_City`  

```csharp
public Unity.Entities.Entity m_City;
```

- `public System.UInt32 m_UpdateFrameIndex`  

```csharp
public System.UInt32 m_UpdateFrameIndex;
```

- `public System.Int32 m_DebugFastGraduationLevel`  

```csharp
public System.Int32 m_DebugFastGraduationLevel;
```


## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private LeaveSchool(System.Int32 chunkIndex, Unity.Entities.Entity entity, Unity.Entities.Entity school) : System.Void`  

```csharp
private System.Void LeaveSchool(System.Int32 chunkIndex, Unity.Entities.Entity entity, Unity.Entities.Entity school);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


