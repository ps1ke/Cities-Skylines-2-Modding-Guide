# Game.Simulation.ZoneSpawnSystem+SpawnBuildingJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct SpawnBuildingJob : Unity.Jobs.IJobParallelFor
{
    public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
    public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_PrefabBuildingData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableObjectData> m_PrefabPlaceableObjectData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> m_PrefabSpawnableObjectData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData;
    public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubArea> m_PrefabSubAreas;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> m_PrefabSubAreaNodes;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubNet> m_PrefabSubNets;
    public Unity.Entities.BufferLookup<Game.Prefabs.PlaceholderObjectElement> m_PrefabPlaceholderElements;
    public Unity.Entities.EntityArchetype m_DefinitionArchetype;
    public Game.Common.RandomSeed m_RandomSeed;
    public System.Boolean m_LefthandTraffic;
    public Game.Simulation.TerrainHeightData m_TerrainHeightData;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_ZoneSearchTree;
    public Game.Prefabs.BuildingConfigurationData m_BuildingConfigurationData;
    public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Residential;
    public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Commercial;
    public Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> m_Industrial;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;

    private System.Void CreateSubNet(System.Int32 jobIndex, Unity.Entities.Entity netPrefab, Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.int2 nodeIndex, Unity.Mathematics.int2 parentMesh, Game.Prefabs.CompositionFlags upgrades, Unity.Collections.NativeList<Unity.Mathematics.float4> nodePositions, Game.Tools.OwnerDefinition ownerDefinition, Unity.Mathematics.Random& random);
    public System.Void Execute(System.Int32 index);
    private System.Single GetMaxHeight(Game.Objects.Transform transform, Game.Prefabs.BuildingData prefabBuildingData);
    private System.Boolean SelectLocation(Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> queue, Game.Simulation.ZoneSpawnSystem+SpawnLocation& location);
    private System.Void Spawn(System.Int32 jobIndex, Game.Simulation.ZoneSpawnSystem+SpawnLocation location, Unity.Mathematics.Random& random);
    private System.Void Spawn(System.Int32 jobIndex, Game.Tools.OwnerDefinition ownerDefinition, Unity.Entities.DynamicBuffer<Game.Prefabs.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodes, Game.Prefabs.BuildingData prefabBuildingData, Unity.Mathematics.Random& random);
    private System.Void Spawn(System.Int32 jobIndex, Game.Tools.OwnerDefinition ownerDefinition, Unity.Entities.DynamicBuffer<Game.Prefabs.SubNet> subNets, Unity.Mathematics.Random& random);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_PrefabBuildingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_PrefabBuildingData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableObjectData> m_PrefabPlaceableObjectData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableObjectData> m_PrefabPlaceableObjectData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> m_PrefabSpawnableObjectData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> m_PrefabSpawnableObjectData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData;
```

- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  

```csharp
public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubArea> m_PrefabSubAreas`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubArea> m_PrefabSubAreas;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> m_PrefabSubAreaNodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> m_PrefabSubAreaNodes;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubNet> m_PrefabSubNets`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubNet> m_PrefabSubNets;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.PlaceholderObjectElement> m_PrefabPlaceholderElements`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.PlaceholderObjectElement> m_PrefabPlaceholderElements;
```

- `public Unity.Entities.EntityArchetype m_DefinitionArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_DefinitionArchetype;
```

- `public Game.Common.RandomSeed m_RandomSeed`  

```csharp
public Game.Common.RandomSeed m_RandomSeed;
```

- `public System.Boolean m_LefthandTraffic`  

```csharp
public System.Boolean m_LefthandTraffic;
```

- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  

```csharp
public Game.Simulation.TerrainHeightData m_TerrainHeightData;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_ZoneSearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_ZoneSearchTree;
```

- `public Game.Prefabs.BuildingConfigurationData m_BuildingConfigurationData`  

```csharp
public Game.Prefabs.BuildingConfigurationData m_BuildingConfigurationData;
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

- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
```


## Methods

- `private CreateSubNet(System.Int32 jobIndex, Unity.Entities.Entity netPrefab, Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.int2 nodeIndex, Unity.Mathematics.int2 parentMesh, Game.Prefabs.CompositionFlags upgrades, Unity.Collections.NativeList<Unity.Mathematics.float4> nodePositions, Game.Tools.OwnerDefinition ownerDefinition, Unity.Mathematics.Random& random) : System.Void`  

```csharp
private System.Void CreateSubNet(System.Int32 jobIndex, Unity.Entities.Entity netPrefab, Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.int2 nodeIndex, Unity.Mathematics.int2 parentMesh, Game.Prefabs.CompositionFlags upgrades, Unity.Collections.NativeList<Unity.Mathematics.float4> nodePositions, Game.Tools.OwnerDefinition ownerDefinition, Unity.Mathematics.Random& random);
```

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```

- `private GetMaxHeight(Game.Objects.Transform transform, Game.Prefabs.BuildingData prefabBuildingData) : System.Single`  

```csharp
private System.Single GetMaxHeight(Game.Objects.Transform transform, Game.Prefabs.BuildingData prefabBuildingData);
```

- `private SelectLocation(Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> queue, Game.Simulation.ZoneSpawnSystem+SpawnLocation& location) : System.Boolean`  

```csharp
private System.Boolean SelectLocation(Unity.Collections.NativeQueue<Game.Simulation.ZoneSpawnSystem+SpawnLocation> queue, Game.Simulation.ZoneSpawnSystem+SpawnLocation& location);
```

- `private Spawn(System.Int32 jobIndex, Game.Simulation.ZoneSpawnSystem+SpawnLocation location, Unity.Mathematics.Random& random) : System.Void`  

```csharp
private System.Void Spawn(System.Int32 jobIndex, Game.Simulation.ZoneSpawnSystem+SpawnLocation location, Unity.Mathematics.Random& random);
```

- `private Spawn(System.Int32 jobIndex, Game.Tools.OwnerDefinition ownerDefinition, Unity.Entities.DynamicBuffer<Game.Prefabs.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodes, Game.Prefabs.BuildingData prefabBuildingData, Unity.Mathematics.Random& random) : System.Void`  

```csharp
private System.Void Spawn(System.Int32 jobIndex, Game.Tools.OwnerDefinition ownerDefinition, Unity.Entities.DynamicBuffer<Game.Prefabs.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodes, Game.Prefabs.BuildingData prefabBuildingData, Unity.Mathematics.Random& random);
```

- `private Spawn(System.Int32 jobIndex, Game.Tools.OwnerDefinition ownerDefinition, Unity.Entities.DynamicBuffer<Game.Prefabs.SubNet> subNets, Unity.Mathematics.Random& random) : System.Void`  

```csharp
private System.Void Spawn(System.Int32 jobIndex, Game.Tools.OwnerDefinition ownerDefinition, Unity.Entities.DynamicBuffer<Game.Prefabs.SubNet> subNets, Unity.Mathematics.Random& random);
```


## Nested types

- `Game.Simulation.ZoneSpawnSystem+SpawnBuildingJob+Iterator`  

