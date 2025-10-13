# Game.Prefabs.ResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabGroup;
    private Unity.Entities.EntityQuery m_InfoGroup;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourcePrefabs;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourceInfos;
    private Unity.Jobs.JobHandle m_PrefabsReaders;
    private System.Int32 m_BaseConsumptionSum;
    private Game.Prefabs.ResourceSystem+TypeHandle __TypeHandle;

    public System.Int32 BaseConsumptionSum { get; }

    public ResourceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddPrefabsReader(Unity.Jobs.JobHandle handle);
    public Unity.Entities.Entity GetPrefab(Game.Economy.Resource resource);
    public Game.Prefabs.ResourcePrefabs GetPrefabs();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_PrefabGroup;
```

- `private Unity.Entities.EntityQuery m_InfoGroup`  

```csharp
private Unity.Entities.EntityQuery m_InfoGroup;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourcePrefabs`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourcePrefabs;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourceInfos`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourceInfos;
```

- `private Unity.Jobs.JobHandle m_PrefabsReaders`  

```csharp
private Unity.Jobs.JobHandle m_PrefabsReaders;
```

- `private System.Int32 m_BaseConsumptionSum`  

```csharp
private System.Int32 m_BaseConsumptionSum;
```

- `private Game.Prefabs.ResourceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ResourceSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 BaseConsumptionSum { get }`  

```csharp
public System.Int32 BaseConsumptionSum { get; }
```


## Constructors

- `public ResourceSystem()`  

```csharp
public ResourceSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddPrefabsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddPrefabsReader(Unity.Jobs.JobHandle handle);
```

- `public GetPrefab(Game.Economy.Resource resource) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity GetPrefab(Game.Economy.Resource resource);
```

- `public GetPrefabs() : Game.Prefabs.ResourcePrefabs`  

```csharp
public Game.Prefabs.ResourcePrefabs GetPrefabs();
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

- `Game.Prefabs.ResourceSystem+TypeHandle`  

