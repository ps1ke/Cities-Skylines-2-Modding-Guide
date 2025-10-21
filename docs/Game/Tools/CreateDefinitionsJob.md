# Game.Tools.NetToolSystem+CreateDefinitionsJob

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CreateDefinitionsJob : Unity.Jobs.IJob
{
    public System.Boolean m_EditorMode;
    public System.Boolean m_RemoveUpgrade;
    public System.Boolean m_LefthandTraffic;
    public Game.Tools.NetToolSystem+Mode m_Mode;
    public Unity.Mathematics.int2 m_ParallelCount;
    public System.Single m_ParallelOffset;
    public Game.Common.RandomSeed m_RandomSeed;
    public Game.Tools.AgeMask m_AgeMask;
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    public Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates;
    public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
    public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.Upgraded> m_UpgradedData;
    public Unity.Entities.ComponentLookup<Game.Net.Fixed> m_FixedData;
    public Unity.Entities.ComponentLookup<Game.Tools.EditorContainer> m_EditorContainerData;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
    public Unity.Entities.ComponentLookup<Game.Tools.LocalTransformCache> m_LocalTransformCacheData;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData;
    public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData;
    public Unity.Entities.ComponentLookup<Game.Buildings.Extension> m_ExtensionData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_NetGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetData> m_PlaceableData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> m_PrefabSpawnableObjectData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData;
    public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges;
    public Unity.Entities.BufferLookup<Game.Net.SubReplacement> m_SubReplacements;
    public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets;
    public Unity.Entities.BufferLookup<Game.Tools.LocalNodeCache> m_CachedNodes;
    public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
    public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
    public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubObject> m_PrefabSubObjects;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubNet> m_PrefabSubNets;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubArea> m_PrefabSubAreas;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> m_PrefabSubAreaNodes;
    public Unity.Entities.BufferLookup<Game.Prefabs.PlaceholderObjectElement> m_PrefabPlaceholderElements;
    public Unity.Entities.Entity m_NetPrefab;
    public Unity.Entities.Entity m_LanePrefab;
    public Unity.Entities.Entity m_ServiceUpgradeOwner;
    public Game.Simulation.WaterSurfaceData m_WaterSurfaceData;
    public Unity.Entities.EntityCommandBuffer m_CommandBuffer;

    private System.Single CalculatedInverseWeight(Game.Tools.NetCourse course, Game.Net.PlacementFlags placementFlags);
    private System.Void CreateComplexCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
    private System.Void CreateContinuousCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
    private System.Void CreateCourseObject(Unity.Entities.Entity prefab, Game.Objects.Transform transform, Game.Tools.OwnerDefinition ownerDefinition, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& selectedSpawnables);
    private System.Void CreateGrid(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
    private System.Void CreateParallelCourse(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, Game.Tools.NetCourse courseData2, System.Single parallelOffset, System.Single elevationLimit, System.Boolean invert, System.Boolean isLeft, System.Boolean isRight, System.Int32 level, Unity.Mathematics.Random& random);
    private System.Void CreateParallelCourse(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, System.Single elevationLimit, System.Boolean invert, System.Boolean isLeft, System.Boolean isRight, Unity.Mathematics.Random& random);
    private System.Void CreateParallelCourses(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.float4, Unity.Mathematics.float3> nodeMap);
    private System.Void CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
    private System.Void CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.ControlPoint point, System.Boolean isStart, System.Boolean isEnd);
    private System.Void CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Entities.Entity edge, System.Boolean invert, System.Boolean isStart, System.Boolean isEnd);
    private System.Void CreateSimpleCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, System.Int32 middleIndex);
    private System.Void CreateSinglePoint(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
    private System.Void CreateStraightLine(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Mathematics.int2 index);
    private System.Void CreateSubAreas(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& selectedSpawnables);
    private System.Void CreateSubNets(Game.Objects.Transform transform, Unity.Entities.Entity prefab);
    private System.Void CreateUpgrade(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Tools.ControlPoint point, System.Boolean isStart, System.Boolean isEnd);
    private System.Void CreateUpgrade(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Entities.Entity edge, Game.Tools.NetToolSystem+UpgradeState upgradeState, System.Boolean invert, System.Boolean isStart, System.Boolean isEnd);
    public System.Void Execute();
    private System.Void FixElevation(Game.Tools.ControlPoint& controlPoint);
    private Game.Objects.Transform GetCourseObjectTransform(Game.Prefabs.SubObject subObject, Game.Tools.CoursePos startPos, Game.Tools.CoursePos endPos);
    private Game.Tools.CoursePos GetCoursePos(Colossal.Mathematics.Bezier4x3 curve, Game.Tools.ControlPoint controlPoint, System.Single courseDelta);
    private System.Single GetCutPosition(Game.Prefabs.NetGeometryData netGeometryData, System.Single length, System.Single t);
    private System.Boolean GetLocalCurve(Game.Tools.NetCourse course, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.LocalCurveCache& localCurveCache);
    private System.Boolean GetOwnerDefinition(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Entities.Entity original, System.Boolean checkControlPoints, Game.Tools.CoursePos startPos, Game.Tools.CoursePos endPos, Game.Tools.OwnerDefinition& ownerDefinition);
    private System.Boolean HasEdgeStartOrEnd(Unity.Entities.Entity node, Unity.Entities.Entity owner);
    private System.Void InvertCourse(Game.Tools.NetCourse& course);
    private System.Void LinearizeElevation(Colossal.Mathematics.Bezier4x3& curve);
    private System.Void LinearizeElevation(Colossal.Mathematics.Bezier4x3& curve1, Colossal.Mathematics.Bezier4x3& curve2);
    private System.Void SetHeight(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint& controlPoint);
    private Colossal.Mathematics.Bezier4x3 TransformCurve(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation);
    private System.Void UpdateOwnerObject(Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity attachedParent, Game.Objects.Transform transform);
    private System.Void UpdateSubAreas(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.Entity original);
    private System.Void UpdateSubNets(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.Entity original);
}
```


## Fields

- `public System.Boolean m_EditorMode`  

```csharp
public System.Boolean m_EditorMode;
```

- `public System.Boolean m_RemoveUpgrade`  

```csharp
public System.Boolean m_RemoveUpgrade;
```

- `public System.Boolean m_LefthandTraffic`  

```csharp
public System.Boolean m_LefthandTraffic;
```

- `public Game.Tools.NetToolSystem+Mode m_Mode`  

```csharp
public Game.Tools.NetToolSystem+Mode m_Mode;
```

- `public Unity.Mathematics.int2 m_ParallelCount`  

```csharp
public Unity.Mathematics.int2 m_ParallelCount;
```

- `public System.Single m_ParallelOffset`  

```csharp
public System.Single m_ParallelOffset;
```

- `public Game.Common.RandomSeed m_RandomSeed`  

```csharp
public Game.Common.RandomSeed m_RandomSeed;
```

- `public Game.Tools.AgeMask m_AgeMask`  

```csharp
public Game.Tools.AgeMask m_AgeMask;
```

- `public Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
public Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `public Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates`  

```csharp
public Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Upgraded> m_UpgradedData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Upgraded> m_UpgradedData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Fixed> m_FixedData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Fixed> m_FixedData;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.EditorContainer> m_EditorContainerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.EditorContainer> m_EditorContainerData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.LocalTransformCache> m_LocalTransformCacheData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.LocalTransformCache> m_LocalTransformCacheData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Extension> m_ExtensionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Extension> m_ExtensionData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_NetGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_NetGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetData> m_PlaceableData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetData> m_PlaceableData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> m_PrefabSpawnableObjectData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> m_PrefabSpawnableObjectData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData;
```

- `public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubReplacement> m_SubReplacements`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubReplacement> m_SubReplacements;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets;
```

- `public Unity.Entities.BufferLookup<Game.Tools.LocalNodeCache> m_CachedNodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Tools.LocalNodeCache> m_CachedNodes;
```

- `public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubObject> m_PrefabSubObjects`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubObject> m_PrefabSubObjects;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubNet> m_PrefabSubNets`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubNet> m_PrefabSubNets;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubArea> m_PrefabSubAreas`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubArea> m_PrefabSubAreas;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> m_PrefabSubAreaNodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> m_PrefabSubAreaNodes;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.PlaceholderObjectElement> m_PrefabPlaceholderElements`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.PlaceholderObjectElement> m_PrefabPlaceholderElements;
```

- `public Unity.Entities.Entity m_NetPrefab`  

```csharp
public Unity.Entities.Entity m_NetPrefab;
```

- `public Unity.Entities.Entity m_LanePrefab`  

```csharp
public Unity.Entities.Entity m_LanePrefab;
```

- `public Unity.Entities.Entity m_ServiceUpgradeOwner`  

```csharp
public Unity.Entities.Entity m_ServiceUpgradeOwner;
```

- `public Game.Simulation.WaterSurfaceData m_WaterSurfaceData`  

```csharp
public Game.Simulation.WaterSurfaceData m_WaterSurfaceData;
```

- `public Unity.Entities.EntityCommandBuffer m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer m_CommandBuffer;
```


## Methods

- `private CalculatedInverseWeight(Game.Tools.NetCourse course, Game.Net.PlacementFlags placementFlags) : System.Single`  

```csharp
private System.Single CalculatedInverseWeight(Game.Tools.NetCourse course, Game.Net.PlacementFlags placementFlags);
```

- `private CreateComplexCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  

```csharp
private System.Void CreateComplexCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
```

- `private CreateContinuousCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  

```csharp
private System.Void CreateContinuousCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
```

- `private CreateCourseObject(Unity.Entities.Entity prefab, Game.Objects.Transform transform, Game.Tools.OwnerDefinition ownerDefinition, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& selectedSpawnables) : System.Void`  

```csharp
private System.Void CreateCourseObject(Unity.Entities.Entity prefab, Game.Objects.Transform transform, Game.Tools.OwnerDefinition ownerDefinition, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& selectedSpawnables);
```

- `private CreateGrid(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  

```csharp
private System.Void CreateGrid(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
```

- `private CreateParallelCourse(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, Game.Tools.NetCourse courseData2, System.Single parallelOffset, System.Single elevationLimit, System.Boolean invert, System.Boolean isLeft, System.Boolean isRight, System.Int32 level, Unity.Mathematics.Random& random) : System.Void`  

```csharp
private System.Void CreateParallelCourse(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, Game.Tools.NetCourse courseData2, System.Single parallelOffset, System.Single elevationLimit, System.Boolean invert, System.Boolean isLeft, System.Boolean isRight, System.Int32 level, Unity.Mathematics.Random& random);
```

- `private CreateParallelCourse(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, System.Single elevationLimit, System.Boolean invert, System.Boolean isLeft, System.Boolean isRight, Unity.Mathematics.Random& random) : System.Void`  

```csharp
private System.Void CreateParallelCourse(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, System.Single elevationLimit, System.Boolean invert, System.Boolean isLeft, System.Boolean isRight, Unity.Mathematics.Random& random);
```

- `private CreateParallelCourses(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.float4, Unity.Mathematics.float3> nodeMap) : System.Void`  

```csharp
private System.Void CreateParallelCourses(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.float4, Unity.Mathematics.float3> nodeMap);
```

- `private CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  

```csharp
private System.Void CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
```

- `private CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.ControlPoint point, System.Boolean isStart, System.Boolean isEnd) : System.Void`  

```csharp
private System.Void CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.ControlPoint point, System.Boolean isStart, System.Boolean isEnd);
```

- `private CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Entities.Entity edge, System.Boolean invert, System.Boolean isStart, System.Boolean isEnd) : System.Void`  

```csharp
private System.Void CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Entities.Entity edge, System.Boolean invert, System.Boolean isStart, System.Boolean isEnd);
```

- `private CreateSimpleCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, System.Int32 middleIndex) : System.Void`  

```csharp
private System.Void CreateSimpleCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, System.Int32 middleIndex);
```

- `private CreateSinglePoint(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  

```csharp
private System.Void CreateSinglePoint(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions);
```

- `private CreateStraightLine(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Mathematics.int2 index) : System.Void`  

```csharp
private System.Void CreateStraightLine(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Mathematics.int2 index);
```

- `private CreateSubAreas(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& selectedSpawnables) : System.Void`  

```csharp
private System.Void CreateSubAreas(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& selectedSpawnables);
```

- `private CreateSubNets(Game.Objects.Transform transform, Unity.Entities.Entity prefab) : System.Void`  

```csharp
private System.Void CreateSubNets(Game.Objects.Transform transform, Unity.Entities.Entity prefab);
```

- `private CreateUpgrade(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Tools.ControlPoint point, System.Boolean isStart, System.Boolean isEnd) : System.Void`  

```csharp
private System.Void CreateUpgrade(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Tools.ControlPoint point, System.Boolean isStart, System.Boolean isEnd);
```

- `private CreateUpgrade(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Entities.Entity edge, Game.Tools.NetToolSystem+UpgradeState upgradeState, System.Boolean invert, System.Boolean isStart, System.Boolean isEnd) : System.Void`  

```csharp
private System.Void CreateUpgrade(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Entities.Entity edge, Game.Tools.NetToolSystem+UpgradeState upgradeState, System.Boolean invert, System.Boolean isStart, System.Boolean isEnd);
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private FixElevation(Game.Tools.ControlPoint& controlPoint) : System.Void`  

```csharp
private System.Void FixElevation(Game.Tools.ControlPoint& controlPoint);
```

- `private GetCourseObjectTransform(Game.Prefabs.SubObject subObject, Game.Tools.CoursePos startPos, Game.Tools.CoursePos endPos) : Game.Objects.Transform`  

```csharp
private Game.Objects.Transform GetCourseObjectTransform(Game.Prefabs.SubObject subObject, Game.Tools.CoursePos startPos, Game.Tools.CoursePos endPos);
```

- `private GetCoursePos(Colossal.Mathematics.Bezier4x3 curve, Game.Tools.ControlPoint controlPoint, System.Single courseDelta) : Game.Tools.CoursePos`  

```csharp
private Game.Tools.CoursePos GetCoursePos(Colossal.Mathematics.Bezier4x3 curve, Game.Tools.ControlPoint controlPoint, System.Single courseDelta);
```

- `private GetCutPosition(Game.Prefabs.NetGeometryData netGeometryData, System.Single length, System.Single t) : System.Single`  

```csharp
private System.Single GetCutPosition(Game.Prefabs.NetGeometryData netGeometryData, System.Single length, System.Single t);
```

- `private GetLocalCurve(Game.Tools.NetCourse course, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.LocalCurveCache& localCurveCache) : System.Boolean`  

```csharp
private System.Boolean GetLocalCurve(Game.Tools.NetCourse course, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.LocalCurveCache& localCurveCache);
```

- `private GetOwnerDefinition(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Entities.Entity original, System.Boolean checkControlPoints, Game.Tools.CoursePos startPos, Game.Tools.CoursePos endPos, Game.Tools.OwnerDefinition& ownerDefinition) : System.Boolean`  

```csharp
private System.Boolean GetOwnerDefinition(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Entities.Entity original, System.Boolean checkControlPoints, Game.Tools.CoursePos startPos, Game.Tools.CoursePos endPos, Game.Tools.OwnerDefinition& ownerDefinition);
```

- `private HasEdgeStartOrEnd(Unity.Entities.Entity node, Unity.Entities.Entity owner) : System.Boolean`  

```csharp
private System.Boolean HasEdgeStartOrEnd(Unity.Entities.Entity node, Unity.Entities.Entity owner);
```

- `private InvertCourse(Game.Tools.NetCourse& course) : System.Void`  

```csharp
private System.Void InvertCourse(Game.Tools.NetCourse& course);
```

- `private LinearizeElevation(Colossal.Mathematics.Bezier4x3& curve) : System.Void`  

```csharp
private System.Void LinearizeElevation(Colossal.Mathematics.Bezier4x3& curve);
```

- `private LinearizeElevation(Colossal.Mathematics.Bezier4x3& curve1, Colossal.Mathematics.Bezier4x3& curve2) : System.Void`  

```csharp
private System.Void LinearizeElevation(Colossal.Mathematics.Bezier4x3& curve1, Colossal.Mathematics.Bezier4x3& curve2);
```

- `private SetHeight(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint& controlPoint) : System.Void`  

```csharp
private System.Void SetHeight(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint& controlPoint);
```

- `private TransformCurve(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation) : Colossal.Mathematics.Bezier4x3`  

```csharp
private Colossal.Mathematics.Bezier4x3 TransformCurve(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation);
```

- `private UpdateOwnerObject(Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity attachedParent, Game.Objects.Transform transform) : System.Void`  

```csharp
private System.Void UpdateOwnerObject(Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity attachedParent, Game.Objects.Transform transform);
```

- `private UpdateSubAreas(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.Entity original) : System.Void`  

```csharp
private System.Void UpdateSubAreas(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.Entity original);
```

- `private UpdateSubNets(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.Entity original) : System.Void`  

```csharp
private System.Void UpdateSubNets(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.Entity original);
```


