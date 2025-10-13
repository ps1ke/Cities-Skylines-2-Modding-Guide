# Game.Areas.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
    private Unity.Entities.EntityQuery m_AllAreasQuery;
    private Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Areas.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& triangleCount);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
```

- `private Unity.Entities.EntityQuery m_AllAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllAreasQuery;
```

- `private Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount;
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

- `private Game.Areas.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.SearchSystem+TypeHandle __TypeHandle;
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

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& triangleCount) : Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& triangleCount);
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

- `Game.Areas.SearchSystem+UpdateSearchTreeJob`  
- `Game.Areas.SearchSystem+TypeHandle`  

