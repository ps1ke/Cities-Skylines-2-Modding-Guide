# Game.UI.InGame.HealthcareInfoviewUISystem+CalculateAverageHealthJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CalculateAverageHealthJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.ComponentTypeHandle<Game.Citizens.Household> m_HouseholdType;
    public Unity.Entities.BufferTypeHandle<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenType;
    public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens;
    public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblems;
    public Unity.Collections.NativeArray<System.Single> m_Results;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Household> m_HouseholdType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Citizens.Household> m_HouseholdType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenType;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblems`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblems;
```

- `public Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Single> m_Results;
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


