# Game.Zones.CellCheckHelpers+CollectBlocksJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CollectBlocksJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue1;
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue2;
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue3;
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue4;
    public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> m_ResultList;

    public System.Void Execute();
    private System.Void ProcessQueue(Unity.Collections.NativeQueue<Unity.Entities.Entity> queue);
    private System.Void RemoveDuplicates();
}
```


## Fields

- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue1`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue1;
```

- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue2`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue2;
```

- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue3`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue3;
```

- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue4`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue4;
```

- `public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> m_ResultList`  

```csharp
public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> m_ResultList;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private ProcessQueue(Unity.Collections.NativeQueue<Unity.Entities.Entity> queue) : System.Void`  

```csharp
private System.Void ProcessQueue(Unity.Collections.NativeQueue<Unity.Entities.Entity> queue);
```

- `private RemoveDuplicates() : System.Void`  

```csharp
private System.Void RemoveDuplicates();
```


