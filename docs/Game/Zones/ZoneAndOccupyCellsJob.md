# Game.Zones.CellOccupyJobs+ZoneAndOccupyCellsJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  
- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_DeletedBlockChunks`  
- `public Game.Prefabs.ZonePrefabs m_ZonePrefabs`  
- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  
- `public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_ObjectSearchTree`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Elevation> m_ElevationData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SignatureBuildingData> m_PrefabSignatureBuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceholderBuildingData> m_PrefabPlaceholderBuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_PrefabZoneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> m_PrefabData`  
- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  

## Methods

- `private static ClearOverrideStatus(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells) : System.Void`  
- `public Execute(System.Int32 index) : System.Void`  
- `private SetOccupiedWithHeight(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells) : System.Void`  

## Nested types

- `Game.Zones.CellOccupyJobs+ZoneAndOccupyCellsJob+ObjectIterator`  
- `Game.Zones.CellOccupyJobs+ZoneAndOccupyCellsJob+DeletedBlockIterator`  

