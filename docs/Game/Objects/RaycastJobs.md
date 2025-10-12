# Game.Objects.RaycastJobs

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  
- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  
- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  
- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

## Nested types

- `Game.Objects.RaycastJobs+RaycastStaticObjectsJob`  
- `Game.Objects.RaycastJobs+GetSourceRangesJob`  
- `Game.Objects.RaycastJobs+ExtractLaneObjectsJob`  
- `Game.Objects.RaycastJobs+RaycastMovingObjectsJob`  

