# Game.Prefabs.NetInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetInitializeSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_PlaceholderQuery;
    private Colossal.Collections.NativeValue<Game.Pathfind.PathfindHeuristicData> m_PathfindHeuristicData;
    private Unity.Jobs.JobHandle m_PathfindHeuristicDeps;
    private Game.Net.Layer m_InGameLayersOnce;
    private Game.Net.Layer m_InGameLayersTwice;
    private Game.Prefabs.NetInitializeSystem+TypeHandle __TypeHandle;

    public NetInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddSections(Game.Prefabs.PrefabBase prefab, Game.Prefabs.NetSectionInfo[] source, Unity.Entities.DynamicBuffer<Game.Prefabs.NetGeometrySection> target, Game.Prefabs.NetSectionFlags flags);
    public System.Boolean CanReplace(Game.Prefabs.NetData netData, System.Boolean inGame);
    public Game.Pathfind.PathfindHeuristicData GetHeuristicData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlaceholderQuery;
```

- `private Colossal.Collections.NativeValue<Game.Pathfind.PathfindHeuristicData> m_PathfindHeuristicData`  

```csharp
private Colossal.Collections.NativeValue<Game.Pathfind.PathfindHeuristicData> m_PathfindHeuristicData;
```

- `private Unity.Jobs.JobHandle m_PathfindHeuristicDeps`  

```csharp
private Unity.Jobs.JobHandle m_PathfindHeuristicDeps;
```

- `private Game.Net.Layer m_InGameLayersOnce`  

```csharp
private Game.Net.Layer m_InGameLayersOnce;
```

- `private Game.Net.Layer m_InGameLayersTwice`  

```csharp
private Game.Net.Layer m_InGameLayersTwice;
```

- `private Game.Prefabs.NetInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NetInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetInitializeSystem()`  

```csharp
public NetInitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AddSections(Game.Prefabs.PrefabBase prefab, Game.Prefabs.NetSectionInfo[] source, Unity.Entities.DynamicBuffer<Game.Prefabs.NetGeometrySection> target, Game.Prefabs.NetSectionFlags flags) : System.Void`  

```csharp
private System.Void AddSections(Game.Prefabs.PrefabBase prefab, Game.Prefabs.NetSectionInfo[] source, Unity.Entities.DynamicBuffer<Game.Prefabs.NetGeometrySection> target, Game.Prefabs.NetSectionFlags flags);
```

- `public CanReplace(Game.Prefabs.NetData netData, System.Boolean inGame) : System.Boolean`  

```csharp
public System.Boolean CanReplace(Game.Prefabs.NetData netData, System.Boolean inGame);
```

- `public GetHeuristicData() : Game.Pathfind.PathfindHeuristicData`  

```csharp
public Game.Pathfind.PathfindHeuristicData GetHeuristicData();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Prefabs.NetInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.NetInitializeSystem+InitializeNetDefaultsJob`  
- `Game.Prefabs.NetInitializeSystem+CollectPathfindDataJob`  
- `Game.Prefabs.NetInitializeSystem+TypeHandle`  

