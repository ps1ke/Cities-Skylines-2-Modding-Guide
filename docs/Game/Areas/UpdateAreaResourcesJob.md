# Game.Areas.AreaResourceSystem+UpdateAreaResourcesJob

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.Entity m_City`  
- `public System.Boolean m_FullUpdate`  
- `public Unity.Collections.NativeArray<Unity.Entities.Entity> m_UpdateList`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_ObjectTree`  
- `public Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> m_NaturalResourceData`  
- `public Game.Simulation.CellMapData<Game.Simulation.GroundWater> m_GroundWaterResourceData`  
- `public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_GeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Tree> m_TreeData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Plant> m_PlantData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Damaged> m_DamagedData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> m_ExtractorAreaData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TreeData> m_PrefabTreeData`  
- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_Nodes`  
- `public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_Triangles`  
- `public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  
- `public Unity.Entities.ComponentLookup<Game.Areas.Extractor> m_ExtractorData`  
- `public Unity.Entities.BufferLookup<Game.Areas.WoodResource> m_WoodResources`  
- `public Unity.Entities.BufferLookup<Game.Areas.MapFeatureElement> m_MapFeatureElements`  
- `public Game.Simulation.WaterSurfaceData m_WaterSurfaceData`  
- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  
- `public Colossal.Mathematics.Bounds1 m_BuildableLandMaxSlope`  

## Methods

- `private CalculateNaturalResources(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.Extractor& extractor, Game.Areas.MapFeature mapFeature) : System.Void`  
- `private CalculateNaturalResources(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Mathematics.float4& resources, Unity.Mathematics.float4& renewal, System.Single& groundWater, System.Single& buildableArea) : System.Void`  
- `private CalculateWoodResources(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Game.Areas.Extractor& extractor, Unity.Entities.DynamicBuffer<Game.Areas.WoodResource> woodResources) : System.Void`  
- `public Execute(System.Int32 index) : System.Void`  

## Nested types

- `Game.Areas.AreaResourceSystem+UpdateAreaResourcesJob+WoodResourceComparer`  

