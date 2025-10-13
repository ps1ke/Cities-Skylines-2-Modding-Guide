# Game.Prefabs.MeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeshSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, System.Int32> m_MaterialIndex;
    private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey;
    private Game.Prefabs.MeshSystem+TypeHandle __TypeHandle;

    public MeshSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Int32 GetMaterialIndex(Colossal.IO.AssetDatabase.SurfaceAsset surface);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, System.Int32> m_MaterialIndex`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, System.Int32> m_MaterialIndex;
```

- `private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey`  

```csharp
private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey;
```

- `private Game.Prefabs.MeshSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.MeshSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MeshSystem()`  

```csharp
public MeshSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetMaterialIndex(Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Int32`  

```csharp
public System.Int32 GetMaterialIndex(Colossal.IO.AssetDatabase.SurfaceAsset surface);
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


## Nested types

- `Game.Prefabs.MeshSystem+RemoveBatchGroupsJob`  
- `Game.Prefabs.MeshSystem+InitializeMeshJob`  
- `Game.Prefabs.MeshSystem+TypeHandle`  

