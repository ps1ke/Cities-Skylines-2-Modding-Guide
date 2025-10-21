# Game.Zones.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_UpdatedBlocksQuery;
    private Unity.Entities.EntityQuery m_AllBlocksQuery;
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Zones.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedBlocksQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBlocksQuery;
```

- `private Unity.Entities.EntityQuery m_AllBlocksQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllBlocksQuery;
```

- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Zones.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Zones.SearchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SearchSystem()`  

```csharp
public SearchSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2>`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
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

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Zones.SearchSystem+UpdateSearchTreeJob`  
- `Game.Zones.SearchSystem+TypeHandle`  

