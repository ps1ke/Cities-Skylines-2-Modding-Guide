# Game.City.DevTreeSystem

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DevTreeSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_MilestoneReachedQuery;
    private Unity.Entities.EntityQuery m_DevTreePointsQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.City.DevTreeSystem+TypeHandle __TypeHandle;

    public System.Int32 points { get; set; }

    public DevTreeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Boolean CheckRequirements(Unity.Entities.DynamicBuffer<Game.Prefabs.DevTreeNodeRequirement> requirements, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked);
    private static System.Boolean CheckService(Unity.Entities.Entity service, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void Purchase(Game.Prefabs.DevTreeNodePrefab nodePrefab);
    public System.Void Purchase(Unity.Entities.Entity node);
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_MilestoneReachedQuery`  

```csharp
private Unity.Entities.EntityQuery m_MilestoneReachedQuery;
```

- `private Unity.Entities.EntityQuery m_DevTreePointsQuery`  

```csharp
private Unity.Entities.EntityQuery m_DevTreePointsQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.City.DevTreeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.City.DevTreeSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 points { get; set }`  

```csharp
public System.Int32 points { get; set; }
```


## Constructors

- `public DevTreeSystem()`  

```csharp
public DevTreeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static CheckRequirements(Unity.Entities.DynamicBuffer<Game.Prefabs.DevTreeNodeRequirement> requirements, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked) : System.Boolean`  

```csharp
private static System.Boolean CheckRequirements(Unity.Entities.DynamicBuffer<Game.Prefabs.DevTreeNodeRequirement> requirements, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked);
```

- `private static CheckService(Unity.Entities.Entity service, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked) : System.Boolean`  

```csharp
private static System.Boolean CheckService(Unity.Entities.Entity service, Unity.Entities.ComponentLookup<Game.Prefabs.Locked> locked);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Purchase(Game.Prefabs.DevTreeNodePrefab nodePrefab) : System.Void`  

```csharp
public System.Void Purchase(Game.Prefabs.DevTreeNodePrefab nodePrefab);
```

- `public Purchase(Unity.Entities.Entity node) : System.Void`  

```csharp
public System.Void Purchase(Unity.Entities.Entity node);
```


## Nested types

- `Game.City.DevTreeSystem+AppendPointsJob`  
- `Game.City.DevTreeSystem+TypeHandle`  

