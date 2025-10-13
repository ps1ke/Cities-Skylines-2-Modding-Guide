# Game.Prefabs.InstanceCountSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InstanceCountSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_UpdatedInstancesQuery;
    private Unity.Entities.EntityQuery m_AllInstancesQuery;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_InstanceCounts;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Prefabs.InstanceCountSystem+TypeHandle __TypeHandle;

    public InstanceCountSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddCountReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddCountWriter(Unity.Jobs.JobHandle jobHandle);
    public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> GetInstanceCounts(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedInstancesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedInstancesQuery;
```

- `private Unity.Entities.EntityQuery m_AllInstancesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllInstancesQuery;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_InstanceCounts`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_InstanceCounts;
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

- `private Game.Prefabs.InstanceCountSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.InstanceCountSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InstanceCountSystem()`  

```csharp
public InstanceCountSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddCountReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddCountReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddCountWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddCountWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public GetInstanceCounts(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32>`  

```csharp
public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> GetInstanceCounts(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
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

- `Game.Prefabs.InstanceCountSystem+UpdateCountsJob`  
- `Game.Prefabs.InstanceCountSystem+TypeHandle`  

