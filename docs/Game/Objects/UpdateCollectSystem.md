# Game.Objects.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateCollectSystem : Game.GameSystemBase
{
    private System.Boolean <isUpdated>k__BackingField;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedBounds;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Game.Objects.UpdateCollectSystem+TypeHandle __TypeHandle;

    public System.Boolean isUpdated { get; private set; }

    public UpdateCollectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddBoundsReader(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedBounds(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <isUpdated>k__BackingField`  

```csharp
private System.Boolean <isUpdated>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedBounds`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedBounds;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Game.Objects.UpdateCollectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.UpdateCollectSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean isUpdated { get; private set }`  

```csharp
public System.Boolean isUpdated { get; private set; }
```


## Constructors

- `public UpdateCollectSystem()`  

```csharp
public UpdateCollectSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddBoundsReader(Unity.Jobs.JobHandle handle);
```

- `public GetUpdatedBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedBounds(Unity.Jobs.JobHandle& dependencies);
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Objects.UpdateCollectSystem+CollectUpdatedObjectBoundsJob`  
- `Game.Objects.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Objects.UpdateCollectSystem+TypeHandle`  

