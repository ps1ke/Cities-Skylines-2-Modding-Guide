# Game.UI.InGame.ResidentsSection+CountDistrictHouseholdsJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CountDistrictHouseholdsJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.Entity m_SelectedEntity;
    public Unity.Entities.EntityTypeHandle m_EntityHandle;
    public Unity.Entities.ComponentTypeHandle<Game.Areas.CurrentDistrict> m_CurrentDistrictHandle;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefHandle;
    public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkLookup;
    public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup;
    public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup;
    public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup;
    public Unity.Entities.BufferLookup<Game.Citizens.HouseholdAnimal> m_HouseholdAnimalLookup;
    public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup;
    public Unity.Collections.NativeArray<System.Int32> m_Results;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.Entity m_SelectedEntity`  

```csharp
public Unity.Entities.Entity m_SelectedEntity;
```

- `public Unity.Entities.EntityTypeHandle m_EntityHandle`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityHandle;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Areas.CurrentDistrict> m_CurrentDistrictHandle`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Areas.CurrentDistrict> m_CurrentDistrictHandle;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefHandle`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefHandle;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup;
```

- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup`  

```csharp
public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup;
```

- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdAnimal> m_HouseholdAnimalLookup`  

```csharp
public Unity.Entities.BufferLookup<Game.Citizens.HouseholdAnimal> m_HouseholdAnimalLookup;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult;
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


