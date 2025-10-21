# Game.Objects.RaycastJobs

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class RaycastJobs
{
    private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
    private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
    private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
    private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
}
```


## Methods

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
```

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
```

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
```

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
```


## Nested types

- `Game.Objects.RaycastJobs+RaycastStaticObjectsJob`  
- `Game.Objects.RaycastJobs+GetSourceRangesJob`  
- `Game.Objects.RaycastJobs+ExtractLaneObjectsJob`  
- `Game.Objects.RaycastJobs+RaycastMovingObjectsJob`  

