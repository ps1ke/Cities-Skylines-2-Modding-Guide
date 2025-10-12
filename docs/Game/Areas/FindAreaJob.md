# Game.Areas.RaycastJobs+FindAreaJob

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Fields

- `public System.Boolean m_EditorMode`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.ComponentLookup<Game.Areas.Space> m_SpaceData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Placeholder> m_PlaceholderData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.ServiceUpgrade> m_ServiceUpgradeData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaData`  
- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_Nodes`  
- `public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_Triangles`  
- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  
- `public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastResult> m_TerrainResults`  
- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  

## Nested types

- `Game.Areas.RaycastJobs+FindAreaJob+ValidationData`  
- `Game.Areas.RaycastJobs+FindAreaJob+GroundIterator`  
- `Game.Areas.RaycastJobs+FindAreaJob+OvergroundIterator`  

