# Game.Prefabs.TriggerPrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TriggerPrefabSystem : Game.GameSystemBase
{
    private Game.Prefabs.TriggerPrefabData m_PrefabData;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Game.Prefabs.TriggerPrefabSystem+TypeHandle __TypeHandle;

    public TriggerPrefabSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle handle);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public Game.Prefabs.TriggerPrefabData ReadTriggerPrefabData(Unity.Jobs.JobHandle& dependencies);
}
```


## Fields

- `private Game.Prefabs.TriggerPrefabData m_PrefabData`  

```csharp
private Game.Prefabs.TriggerPrefabData m_PrefabData;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Game.Prefabs.TriggerPrefabSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.TriggerPrefabSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TriggerPrefabSystem()`  

```csharp
public TriggerPrefabSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddReader(Unity.Jobs.JobHandle handle);
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

- `public ReadTriggerPrefabData(Unity.Jobs.JobHandle& dependencies) : Game.Prefabs.TriggerPrefabData`  

```csharp
public Game.Prefabs.TriggerPrefabData ReadTriggerPrefabData(Unity.Jobs.JobHandle& dependencies);
```


## Nested types

- `Game.Prefabs.TriggerPrefabSystem+UpdateTriggerPrefabDataJob`  
- `Game.Prefabs.TriggerPrefabSystem+TypeHandle`  

