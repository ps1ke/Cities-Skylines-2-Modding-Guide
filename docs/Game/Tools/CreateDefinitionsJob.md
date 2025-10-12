# Game.Tools.NetToolSystem+CreateDefinitionsJob

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public System.Boolean m_EditorMode`  
- `public System.Boolean m_RemoveUpgrade`  
- `public System.Boolean m_LefthandTraffic`  
- `public Game.Tools.NetToolSystem+Mode m_Mode`  
- `public Unity.Mathematics.int2 m_ParallelCount`  
- `public System.Single m_ParallelOffset`  
- `public Game.Common.RandomSeed m_RandomSeed`  
- `public Game.Tools.AgeMask m_AgeMask`  
- `public Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  
- `public Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates`  
- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Upgraded> m_UpgradedData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Fixed> m_FixedData`  
- `public Unity.Entities.ComponentLookup<Game.Tools.EditorContainer> m_EditorContainerData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  
- `public Unity.Entities.ComponentLookup<Game.Tools.LocalTransformCache> m_LocalTransformCacheData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Extension> m_ExtensionData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_NetGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetData> m_PlaceableData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> m_PrefabSpawnableObjectData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData`  
- `public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges`  
- `public Unity.Entities.BufferLookup<Game.Net.SubReplacement> m_SubReplacements`  
- `public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets`  
- `public Unity.Entities.BufferLookup<Game.Tools.LocalNodeCache> m_CachedNodes`  
- `public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas`  
- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  
- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.SubObject> m_PrefabSubObjects`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.SubNet> m_PrefabSubNets`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.SubArea> m_PrefabSubAreas`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> m_PrefabSubAreaNodes`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.PlaceholderObjectElement> m_PrefabPlaceholderElements`  
- `public Unity.Entities.Entity m_NetPrefab`  
- `public Unity.Entities.Entity m_LanePrefab`  
- `public Unity.Entities.Entity m_ServiceUpgradeOwner`  
- `public Game.Simulation.WaterSurfaceData m_WaterSurfaceData`  
- `public Unity.Entities.EntityCommandBuffer m_CommandBuffer`  

## Methods

- `private CalculatedInverseWeight(Game.Tools.NetCourse course, Game.Net.PlacementFlags placementFlags) : System.Single`  
- `private CreateComplexCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  
- `private CreateContinuousCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  
- `private CreateCourseObject(Unity.Entities.Entity prefab, Game.Objects.Transform transform, Game.Tools.OwnerDefinition ownerDefinition, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& selectedSpawnables) : System.Void`  
- `private CreateGrid(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  
- `private CreateParallelCourse(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, Game.Tools.NetCourse courseData2, System.Single parallelOffset, System.Single elevationLimit, System.Boolean invert, System.Boolean isLeft, System.Boolean isRight, System.Int32 level, Unity.Mathematics.Random& random) : System.Void`  
- `private CreateParallelCourse(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, System.Single elevationLimit, System.Boolean invert, System.Boolean isLeft, System.Boolean isRight, Unity.Mathematics.Random& random) : System.Void`  
- `private CreateParallelCourses(Game.Tools.CreationDefinition definitionData, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.NetCourse courseData, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.float4, Unity.Mathematics.float3> nodeMap) : System.Void`  
- `private CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  
- `private CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.ControlPoint point, System.Boolean isStart, System.Boolean isEnd) : System.Void`  
- `private CreateReplacement(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint endPoint, Unity.Entities.Entity edge, System.Boolean invert, System.Boolean isStart, System.Boolean isEnd) : System.Void`  
- `private CreateSimpleCurve(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, System.Int32 middleIndex) : System.Void`  
- `private CreateSinglePoint(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions) : System.Void`  
- `private CreateStraightLine(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Mathematics.int2 index) : System.Void`  
- `private CreateSubAreas(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& selectedSpawnables) : System.Void`  
- `private CreateSubNets(Game.Objects.Transform transform, Unity.Entities.Entity prefab) : System.Void`  
- `private CreateUpgrade(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Tools.ControlPoint point, System.Boolean isStart, System.Boolean isEnd) : System.Void`  
- `private CreateUpgrade(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Entities.Entity edge, Game.Tools.NetToolSystem+UpgradeState upgradeState, System.Boolean invert, System.Boolean isStart, System.Boolean isEnd) : System.Void`  
- `public Execute() : System.Void`  
- `private FixElevation(Game.Tools.ControlPoint& controlPoint) : System.Void`  
- `private GetCourseObjectTransform(Game.Prefabs.SubObject subObject, Game.Tools.CoursePos startPos, Game.Tools.CoursePos endPos) : Game.Objects.Transform`  
- `private GetCoursePos(Colossal.Mathematics.Bezier4x3 curve, Game.Tools.ControlPoint controlPoint, System.Single courseDelta) : Game.Tools.CoursePos`  
- `private GetCutPosition(Game.Prefabs.NetGeometryData netGeometryData, System.Single length, System.Single t) : System.Single`  
- `private GetLocalCurve(Game.Tools.NetCourse course, Game.Tools.OwnerDefinition ownerDefinition, Game.Tools.LocalCurveCache& localCurveCache) : System.Boolean`  
- `private GetOwnerDefinition(Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Tools.OwnerDefinition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerDefinitions, Unity.Entities.Entity original, System.Boolean checkControlPoints, Game.Tools.CoursePos startPos, Game.Tools.CoursePos endPos, Game.Tools.OwnerDefinition& ownerDefinition) : System.Boolean`  
- `private HasEdgeStartOrEnd(Unity.Entities.Entity node, Unity.Entities.Entity owner) : System.Boolean`  
- `private InvertCourse(Game.Tools.NetCourse& course) : System.Void`  
- `private LinearizeElevation(Colossal.Mathematics.Bezier4x3& curve) : System.Void`  
- `private LinearizeElevation(Colossal.Mathematics.Bezier4x3& curve1, Colossal.Mathematics.Bezier4x3& curve2) : System.Void`  
- `private SetHeight(Game.Tools.ControlPoint startPoint, Game.Tools.ControlPoint& controlPoint) : System.Void`  
- `private TransformCurve(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation) : Colossal.Mathematics.Bezier4x3`  
- `private UpdateOwnerObject(Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity attachedParent, Game.Objects.Transform transform) : System.Void`  
- `private UpdateSubAreas(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.Entity original) : System.Void`  
- `private UpdateSubNets(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.Entity original) : System.Void`  

