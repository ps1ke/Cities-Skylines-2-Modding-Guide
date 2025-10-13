# Game.Prefabs.NetCompositionMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetCompositionMeshSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_MeshQuery;
    private Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> m_MeshEntities;
    private Unity.Jobs.JobHandle m_Dependencies;
    private Game.Prefabs.NetCompositionMeshSystem+TypeHandle __TypeHandle;

    public NetCompositionMeshSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddMeshEntityReader(Unity.Jobs.JobHandle dependencies);
    public Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> GetMeshEntities(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_MeshQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshQuery;
```

- `private Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> m_MeshEntities`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> m_MeshEntities;
```

- `private Unity.Jobs.JobHandle m_Dependencies`  

```csharp
private Unity.Jobs.JobHandle m_Dependencies;
```

- `private Game.Prefabs.NetCompositionMeshSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NetCompositionMeshSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetCompositionMeshSystem()`  

```csharp
public NetCompositionMeshSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddMeshEntityReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddMeshEntityReader(Unity.Jobs.JobHandle dependencies);
```

- `public GetMeshEntities(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity>`  

```csharp
public Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> GetMeshEntities(Unity.Jobs.JobHandle& dependencies);
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

- `Game.Prefabs.NetCompositionMeshSystem+CompositionMeshJob`  
- `Game.Prefabs.NetCompositionMeshSystem+TypeHandle`  

