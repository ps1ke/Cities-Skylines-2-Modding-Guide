# Game.Simulation.ZoneSpawnSystem+EvaluateSpawnAreas

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct EvaluateSpawnAreas : Unity.Entities.IJobChunk
{
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_BuildingChunks;
    public Game.Prefabs.ZonePrefabs m_ZonePrefabs;
    public Game.Prefabs.ZonePreferenceData m_Preferences;
    public System.Int32 m_SpawnResidential;
    public System.Int32 m_SpawnCommercial;
    public System.Int32 m_SpawnIndustrial;
    public System.Int32 m_SpawnStorage;
    public System.Int32 m_MinDemand;
    public Unity.Mathematics.int3 m_ResidentialDemands;
    public Unity.Collections.NativeArray<System.Int32> m_CommercialBuildingDemands;
    public Unity.Collections.NativeArray<System.Int32> m_IndustrialDemands;
    public Unity.Collections.NativeArray<System.Int32> m_StorageDemands;
    public Game.Common.RandomSeed m_RandomSeed;
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Zones.Block> m_BlockType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    public Unity.Entities.ComponentTypeHandle<Game.Zones.CurvePosition> m_CurvePositionType;
    public Unity.Entities.BufferTypeHandle<Game.Zones.VacantLot> m_VacantLotType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.BuildingData> m_BuildingDataType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryType;
    public Unity.Entities.SharedComponentTypeHandle<Game.Prefabs.BuildingSpawnGroupData> m_BuildingSpawnGroupType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.WarehouseData> m_WarehouseType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ZonePropertiesData> m_ZonePropertiesDatas;
    public Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities;
    public Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> m_Processes;
    public Unity.Entities.BufferLookup<Game.Zones.ProcessEstimate> m_ProcessEstimates;
    public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues;
    public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
    public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;
    public Unity.Collections.NativeArray<Game.Simulation.GroundPollution> m_PollutionMap;
    public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Residential;
    public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Commercial;
    public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Industrial;

    private System.Single CalculateCurvePos(Game.Zones.CurvePosition curvePosition, Game.Zones.VacantLot lot, Game.Zones.Block block);
    private System.Int32 EvaluateDemandAndAvailability(Game.Prefabs.BuildingPropertyData buildingPropertyData, Game.Zones.AreaType areaType, Game.Prefabs.ZoneDensity zoneDensity, System.Boolean storage);
    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Boolean SelectBuilding(Game.Simulation.ZoneSpawnSystem+SpawnLocation& location, Unity.Mathematics.Random& random, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.ZoneData zoneData, Game.Prefabs.ZonePropertiesData zonePropertiesData, System.Single curvePos, System.Single pollution, System.Single landValue, System.Single maxHeight, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, System.Boolean normal, System.Boolean storage, System.Boolean extractor, System.Boolean office);
    private System.Void TryAddLot(Game.Simulation.ZoneSpawnSystem+SpawnLocation& bestLocation, Unity.Mathematics.Random& random, Unity.Entities.Entity road, System.Single curvePos, Unity.Entities.Entity entity, Unity.Mathematics.int4 area, Game.Zones.LotFlags flags, System.Int32 height, Game.Prefabs.ZoneData zoneData, Game.Prefabs.ZonePropertiesData zonePropertiesData, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, System.Boolean normal, System.Boolean storage);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_BuildingChunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_BuildingChunks;
```

- `public Game.Prefabs.ZonePrefabs m_ZonePrefabs`  

```csharp
public Game.Prefabs.ZonePrefabs m_ZonePrefabs;
```

- `public Game.Prefabs.ZonePreferenceData m_Preferences`  

```csharp
public Game.Prefabs.ZonePreferenceData m_Preferences;
```

- `public System.Int32 m_SpawnResidential`  

```csharp
public System.Int32 m_SpawnResidential;
```

- `public System.Int32 m_SpawnCommercial`  

```csharp
public System.Int32 m_SpawnCommercial;
```

- `public System.Int32 m_SpawnIndustrial`  

```csharp
public System.Int32 m_SpawnIndustrial;
```

- `public System.Int32 m_SpawnStorage`  

```csharp
public System.Int32 m_SpawnStorage;
```

- `public System.Int32 m_MinDemand`  

```csharp
public System.Int32 m_MinDemand;
```

- `public Unity.Mathematics.int3 m_ResidentialDemands`  

```csharp
public Unity.Mathematics.int3 m_ResidentialDemands;
```

- `public Unity.Collections.NativeArray<System.Int32> m_CommercialBuildingDemands`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_CommercialBuildingDemands;
```

- `public Unity.Collections.NativeArray<System.Int32> m_IndustrialDemands`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_IndustrialDemands;
```

- `public Unity.Collections.NativeArray<System.Int32> m_StorageDemands`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_StorageDemands;
```

- `public Game.Common.RandomSeed m_RandomSeed`  

```csharp
public Game.Common.RandomSeed m_RandomSeed;
```

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Zones.Block> m_BlockType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Zones.Block> m_BlockType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Zones.CurvePosition> m_CurvePositionType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Zones.CurvePosition> m_CurvePositionType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Zones.VacantLot> m_VacantLotType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Zones.VacantLot> m_VacantLotType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.BuildingData> m_BuildingDataType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.BuildingData> m_BuildingDataType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryType;
```

- `public Unity.Entities.SharedComponentTypeHandle<Game.Prefabs.BuildingSpawnGroupData> m_BuildingSpawnGroupType`  

```csharp
public Unity.Entities.SharedComponentTypeHandle<Game.Prefabs.BuildingSpawnGroupData> m_BuildingSpawnGroupType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.WarehouseData> m_WarehouseType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.WarehouseData> m_WarehouseType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZonePropertiesData> m_ZonePropertiesDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ZonePropertiesData> m_ZonePropertiesDatas;
```

- `public Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities;
```

- `public Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> m_Processes`  

```csharp
public Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> m_Processes;
```

- `public Unity.Entities.BufferLookup<Game.Zones.ProcessEstimate> m_ProcessEstimates`  

```csharp
public Unity.Entities.BufferLookup<Game.Zones.ProcessEstimate> m_ProcessEstimates;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
```

- `public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  

```csharp
public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;
```

- `public Unity.Collections.NativeArray<Game.Simulation.GroundPollution> m_PollutionMap`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.GroundPollution> m_PollutionMap;
```

- `public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Residential`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Residential;
```

- `public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Commercial`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Commercial;
```

- `public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Industrial`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Industrial;
```


## Methods

- `private CalculateCurvePos(Game.Zones.CurvePosition curvePosition, Game.Zones.VacantLot lot, Game.Zones.Block block) : System.Single`  

```csharp
private System.Single CalculateCurvePos(Game.Zones.CurvePosition curvePosition, Game.Zones.VacantLot lot, Game.Zones.Block block);
```

- `private EvaluateDemandAndAvailability(Game.Prefabs.BuildingPropertyData buildingPropertyData, Game.Zones.AreaType areaType, Game.Prefabs.ZoneDensity zoneDensity, System.Boolean storage = False) : System.Int32`  

```csharp
private System.Int32 EvaluateDemandAndAvailability(Game.Prefabs.BuildingPropertyData buildingPropertyData, Game.Zones.AreaType areaType, Game.Prefabs.ZoneDensity zoneDensity, System.Boolean storage);
```

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private SelectBuilding(Game.Simulation.ZoneSpawnSystem+SpawnLocation& location, Unity.Mathematics.Random& random, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.ZoneData zoneData, Game.Prefabs.ZonePropertiesData zonePropertiesData, System.Single curvePos, System.Single pollution, System.Single landValue, System.Single maxHeight, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, System.Boolean normal = True, System.Boolean storage = False, System.Boolean extractor = False, System.Boolean office = False) : System.Boolean`  

```csharp
private System.Boolean SelectBuilding(Game.Simulation.ZoneSpawnSystem+SpawnLocation& location, Unity.Mathematics.Random& random, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.ZoneData zoneData, Game.Prefabs.ZonePropertiesData zonePropertiesData, System.Single curvePos, System.Single pollution, System.Single landValue, System.Single maxHeight, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, System.Boolean normal, System.Boolean storage, System.Boolean extractor, System.Boolean office);
```

- `private TryAddLot(Game.Simulation.ZoneSpawnSystem+SpawnLocation& bestLocation, Unity.Mathematics.Random& random, Unity.Entities.Entity road, System.Single curvePos, Unity.Entities.Entity entity, Unity.Mathematics.int4 area, Game.Zones.LotFlags flags, System.Int32 height, Game.Prefabs.ZoneData zoneData, Game.Prefabs.ZonePropertiesData zonePropertiesData, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, System.Boolean normal = True, System.Boolean storage = False) : System.Void`  

```csharp
private System.Void TryAddLot(Game.Simulation.ZoneSpawnSystem+SpawnLocation& bestLocation, Unity.Mathematics.Random& random, Unity.Entities.Entity road, System.Single curvePos, Unity.Entities.Entity entity, Unity.Mathematics.int4 area, Game.Zones.LotFlags flags, System.Int32 height, Game.Prefabs.ZoneData zoneData, Game.Prefabs.ZonePropertiesData zonePropertiesData, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, System.Boolean normal, System.Boolean storage);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


