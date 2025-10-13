# Game.Objects.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_UpdatedStaticsQuery;
    private Unity.Entities.EntityQuery m_AllStaticsQuery;
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticSearchTree;
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingSearchTree;
    private Unity.Jobs.JobHandle m_StaticReadDependencies;
    private Unity.Jobs.JobHandle m_StaticWriteDependencies;
    private Unity.Jobs.JobHandle m_MovingReadDependencies;
    private Unity.Jobs.JobHandle m_MovingWriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Objects.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddMovingSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddMovingSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddStaticSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddStaticSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetMovingSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetStaticSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedStaticsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedStaticsQuery;
```

- `private Unity.Entities.EntityQuery m_AllStaticsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllStaticsQuery;
```

- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticSearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticSearchTree;
```

- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingSearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingSearchTree;
```

- `private Unity.Jobs.JobHandle m_StaticReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_StaticReadDependencies;
```

- `private Unity.Jobs.JobHandle m_StaticWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_StaticWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_MovingReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_MovingReadDependencies;
```

- `private Unity.Jobs.JobHandle m_MovingWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_MovingWriteDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Objects.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SearchSystem+TypeHandle __TypeHandle;
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

- `public AddMovingSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddMovingSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddMovingSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddMovingSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public AddStaticSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddStaticSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddStaticSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddStaticSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetMovingSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetMovingSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `public GetStaticSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetStaticSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
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

- `Game.Objects.SearchSystem+UpdateSearchTreeJob`  
- `Game.Objects.SearchSystem+TypeHandle`  

