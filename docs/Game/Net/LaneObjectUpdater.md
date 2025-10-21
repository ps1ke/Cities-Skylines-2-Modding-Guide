# Game.Net.LaneObjectUpdater

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LaneObjectUpdater
{
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
    private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue;
    private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue;

    public LaneObjectUpdater(Unity.Entities.SystemBase system);

    public Unity.Jobs.JobHandle Apply(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle dependencies);
    public Game.Net.LaneObjectCommandBuffer Begin(Unity.Collections.Allocator allocator);
}
```


## Fields

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  

```csharp
private Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
```

- `private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue`  

```csharp
private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue;
```

- `private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue;
```


## Constructors

- `public LaneObjectUpdater(Unity.Entities.SystemBase system)`  

```csharp
public LaneObjectUpdater(Unity.Entities.SystemBase system);
```


## Methods

- `public Apply(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle dependencies) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle Apply(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle dependencies);
```

- `public Begin(Unity.Collections.Allocator allocator) : Game.Net.LaneObjectCommandBuffer`  

```csharp
public Game.Net.LaneObjectCommandBuffer Begin(Unity.Collections.Allocator allocator);
```


## Nested types

- `Game.Net.LaneObjectUpdater+UpdateLaneObjectsJob`  
- `Game.Net.LaneObjectUpdater+UpdateTreeObjectsJob`  

