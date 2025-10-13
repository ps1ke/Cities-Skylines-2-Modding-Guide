# Game.Objects.RaycastJobs+ExtractLaneObjectsJob

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ExtractLaneObjectsJob : Unity.Jobs.IJobParallelFor
{
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
    public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData;
    public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
    public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges;
    public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_EdgeList;
    public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_StaticObjectList;
    public Unity.Collections.NativeArray<Unity.Mathematics.int4> m_Ranges;
    public Unity.Collections.NativeQueue<Game.Common.RaycastSystem+EntityResult> m_MovingObjectQueue;

    private System.Void CheckLanes(System.Int32 raycastIndex, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes);
    public System.Void Execute(System.Int32 index);
    private System.Void TryCheckLanes(Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult entity);
    private System.Void TryCheckNode(Game.Common.RaycastInput input, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult node, Unity.Entities.Entity ignoreEdge);
    private System.Void TryCheckObject(Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult obj);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
```

- `public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges;
```

- `public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_EdgeList`  

```csharp
public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_EdgeList;
```

- `public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_StaticObjectList`  

```csharp
public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_StaticObjectList;
```

- `public Unity.Collections.NativeArray<Unity.Mathematics.int4> m_Ranges`  

```csharp
public Unity.Collections.NativeArray<Unity.Mathematics.int4> m_Ranges;
```

- `public Unity.Collections.NativeQueue<Game.Common.RaycastSystem+EntityResult> m_MovingObjectQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Common.RaycastSystem+EntityResult> m_MovingObjectQueue;
```


## Methods

- `private CheckLanes(System.Int32 raycastIndex, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes) : System.Void`  

```csharp
private System.Void CheckLanes(System.Int32 raycastIndex, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes);
```

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```

- `private TryCheckLanes(Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult entity) : System.Void`  

```csharp
private System.Void TryCheckLanes(Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult entity);
```

- `private TryCheckNode(Game.Common.RaycastInput input, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult node, Unity.Entities.Entity ignoreEdge) : System.Void`  

```csharp
private System.Void TryCheckNode(Game.Common.RaycastInput input, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult node, Unity.Entities.Entity ignoreEdge);
```

- `private TryCheckObject(Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult obj) : System.Void`  

```csharp
private System.Void TryCheckObject(Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> checkedEntities, Game.Common.RaycastSystem+EntityResult obj);
```


