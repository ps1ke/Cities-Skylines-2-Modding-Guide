# Game.Net.LaneObjectCommandBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LaneObjectCommandBuffer
{
    private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue;
    private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue;

    public LaneObjectCommandBuffer(Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> laneActionQueue, Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> treeActionQueue);

    public System.Void Add(Unity.Entities.Entity lane, Unity.Entities.Entity entity, Unity.Mathematics.float2 curvePosition);
    public System.Void Add(Unity.Entities.Entity entity, Colossal.Mathematics.Bounds3 bounds);
    public System.Void Remove(Unity.Entities.Entity lane, Unity.Entities.Entity entity);
    public System.Void Remove(Unity.Entities.Entity entity);
    public System.Void Update(Unity.Entities.Entity lane, Unity.Entities.Entity entity, Unity.Mathematics.float2 curvePosition);
    public System.Void Update(Unity.Entities.Entity entity, Colossal.Mathematics.Bounds3 bounds);
}
```


## Fields

- `private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue`  

```csharp
private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue;
```

- `private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue;
```


## Constructors

- `public LaneObjectCommandBuffer(Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> laneActionQueue, Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> treeActionQueue)`  

```csharp
public LaneObjectCommandBuffer(NativeParallelQueue<LaneObjectAction>.Writer laneActionQueue, NativeQueue<TreeObjectAction>.ParallelWriter treeActionQueue)
	{
		m_LaneActionQueue = laneActionQueue;
		m_TreeActionQueue = treeActionQueue;
	}
```


## Methods

- `public Add(Unity.Entities.Entity lane, Unity.Entities.Entity entity, Unity.Mathematics.float2 curvePosition) : System.Void`  

```csharp
public void Add(Entity entity, Bounds3 bounds)
	{
		m_TreeActionQueue.Enqueue(new TreeObjectAction(entity, bounds));
	}
```

- `public Add(Unity.Entities.Entity entity, Colossal.Mathematics.Bounds3 bounds) : System.Void`  

```csharp
public void Add(Entity entity, Bounds3 bounds)
	{
		m_TreeActionQueue.Enqueue(new TreeObjectAction(entity, bounds));
	}
```

- `public Remove(Unity.Entities.Entity lane, Unity.Entities.Entity entity) : System.Void`  

```csharp
public void Remove(Entity entity)
	{
		m_TreeActionQueue.Enqueue(new TreeObjectAction(entity));
	}
```

- `public Remove(Unity.Entities.Entity entity) : System.Void`  

```csharp
public void Remove(Entity entity)
	{
		m_TreeActionQueue.Enqueue(new TreeObjectAction(entity));
	}
```

- `public Update(Unity.Entities.Entity lane, Unity.Entities.Entity entity, Unity.Mathematics.float2 curvePosition) : System.Void`  

```csharp
public void Update(Entity entity, Bounds3 bounds)
	{
		m_TreeActionQueue.Enqueue(new TreeObjectAction(entity, entity, bounds));
	}
```

- `public Update(Unity.Entities.Entity entity, Colossal.Mathematics.Bounds3 bounds) : System.Void`  

```csharp
public void Update(Entity entity, Bounds3 bounds)
	{
		m_TreeActionQueue.Enqueue(new TreeObjectAction(entity, entity, bounds));
	}
```


