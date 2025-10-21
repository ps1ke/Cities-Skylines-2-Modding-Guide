# Game.Prefabs.ReplacePrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ReplacePrefabSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.ReplacePrefabSystem+Finalize m_FinalizeSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PrefabRefQuery;
    private Unity.Entities.Entity m_OldPrefab;
    private Unity.Entities.Entity m_NewPrefab;
    private Unity.Entities.Entity m_SourceInstance;
    private Unity.Collections.NativeList<Game.Prefabs.ReplacePrefabSystem+ReplaceMesh> m_MeshReplaces;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdateInstances;
    private Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData> m_ReplacePrefabData;
    private Game.Prefabs.ReplacePrefabSystem+TypeHandle __TypeHandle;

    public ReplacePrefabSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CheckInstanceComponents(Unity.Entities.Entity instance, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> checkedComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> archetypeComponents);
    public System.Void FinalizeReplaces();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void ReplacePrefab(Unity.Entities.Entity oldPrefab, Unity.Entities.Entity newPrefab, Unity.Entities.Entity sourceInstance);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.ReplacePrefabSystem+Finalize m_FinalizeSystem`  

```csharp
private Game.Prefabs.ReplacePrefabSystem+Finalize m_FinalizeSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabRefQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabRefQuery;
```

- `private Unity.Entities.Entity m_OldPrefab`  

```csharp
private Unity.Entities.Entity m_OldPrefab;
```

- `private Unity.Entities.Entity m_NewPrefab`  

```csharp
private Unity.Entities.Entity m_NewPrefab;
```

- `private Unity.Entities.Entity m_SourceInstance`  

```csharp
private Unity.Entities.Entity m_SourceInstance;
```

- `private Unity.Collections.NativeList<Game.Prefabs.ReplacePrefabSystem+ReplaceMesh> m_MeshReplaces`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.ReplacePrefabSystem+ReplaceMesh> m_MeshReplaces;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdateInstances`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdateInstances;
```

- `private Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData> m_ReplacePrefabData`  

```csharp
private Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData> m_ReplacePrefabData;
```

- `private Game.Prefabs.ReplacePrefabSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ReplacePrefabSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ReplacePrefabSystem()`  

```csharp
public ReplacePrefabSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CheckInstanceComponents(Unity.Entities.Entity instance, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> checkedComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> archetypeComponents) : System.Void`  

```csharp
private System.Void CheckInstanceComponents(Unity.Entities.Entity instance, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> checkedComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> archetypeComponents);
```

- `public FinalizeReplaces() : System.Void`  

```csharp
public System.Void FinalizeReplaces();
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

- `public ReplacePrefab(Unity.Entities.Entity oldPrefab, Unity.Entities.Entity newPrefab, Unity.Entities.Entity sourceInstance) : System.Void`  

```csharp
public System.Void ReplacePrefab(Unity.Entities.Entity oldPrefab, Unity.Entities.Entity newPrefab, Unity.Entities.Entity sourceInstance);
```


## Nested types

- `Game.Prefabs.ReplacePrefabSystem+ReplaceMesh`  
- `Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData`  
- `Game.Prefabs.ReplacePrefabSystem+Finalize`  
- `Game.Prefabs.ReplacePrefabSystem+RemoveBatchGroupsJob`  
- `Game.Prefabs.ReplacePrefabSystem+ReplacePrefabJob`  
- `Game.Prefabs.ReplacePrefabSystem+TypeHandle`  

