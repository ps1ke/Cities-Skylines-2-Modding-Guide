# Game.Objects.RaycastJobs+ExtractLaneObjectsJob

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData`  
- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  
- `public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges`  
- `public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_EdgeList`  
- `public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_StaticObjectList`  
- `public Unity.Collections.NativeArray<Unity.Mathematics.int4> m_Ranges`  
- `public Unity.Collections.NativeQueue<Game.Common.RaycastSystem+EntityResult> m_MovingObjectQueue`  

## Methods

- `private CheckLanes(System.Int32 raycastIndex, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes) : System.Void`  
- `public Execute(System.Int32 index) : System.Void`  
- `private TryCheckLanes(Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult entity) : System.Void`  
- `private TryCheckNode(Game.Common.RaycastInput input, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult node, Unity.Entities.Entity ignoreEdge) : System.Void`  
- `private TryCheckObject(Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult obj) : System.Void`  

