# Game.Simulation.PropertyProcessingSystem+PutPropertyOnMarketJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct PutPropertyOnMarketJob : Unity.Entities.IJobChunk
{
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_CommercialCompanyPrefabs;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_IndustrialCompanyPrefabs;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ArchetypeData> m_Archetypes;
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas;
    public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
    public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
    public Unity.Entities.ComponentLookup<Game.Areas.Lot> m_Lots;
    public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_Geometries;
    public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attacheds;
    public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues;
    public Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertyOnMarkets;
    public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_Abandoneds;
    public Game.Prefabs.EconomyParameterData m_EconomyParameterData;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_CommercialCompanyPrefabs`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_CommercialCompanyPrefabs;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_IndustrialCompanyPrefabs`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_IndustrialCompanyPrefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ArchetypeData> m_Archetypes`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ArchetypeData> m_Archetypes;
```

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType;
```

- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas;
```

- `public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
```

- `public Unity.Entities.ComponentLookup<Game.Areas.Lot> m_Lots`  

```csharp
public Unity.Entities.ComponentLookup<Game.Areas.Lot> m_Lots;
```

- `public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_Geometries`  

```csharp
public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_Geometries;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attacheds`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attacheds;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertyOnMarkets`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertyOnMarkets;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_Abandoneds`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_Abandoneds;
```

- `public Game.Prefabs.EconomyParameterData m_EconomyParameterData`  

```csharp
public Game.Prefabs.EconomyParameterData m_EconomyParameterData;
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


