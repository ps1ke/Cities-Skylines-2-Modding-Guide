# Game.Net.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateCollectSystem : Game.GameSystemBase
{
    private System.Boolean <netsUpdated>k__BackingField;
    private System.Boolean <lanesUpdated>k__BackingField;
    private Unity.Entities.EntityQuery m_NetGeometryQuery;
    private Unity.Entities.EntityQuery m_LaneGeometryQuery;
    private Game.Net.SearchSystem m_SearchSystem;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedNetBounds;
    private Unity.Jobs.JobHandle m_NetWriteDependencies;
    private Unity.Jobs.JobHandle m_NetReadDependencies;
    private Unity.Jobs.JobHandle m_LaneWriteDependencies;
    private Unity.Jobs.JobHandle m_LaneReadDependencies;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedLaneBounds;
    private Game.Net.UpdateCollectSystem+TypeHandle __TypeHandle;

    public System.Boolean netsUpdated { get; private set; }
    public System.Boolean lanesUpdated { get; private set; }

    public UpdateCollectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddLaneBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddNetBoundsReader(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedLaneBounds(Unity.Jobs.JobHandle& dependencies);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedNetBounds(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <netsUpdated>k__BackingField`  

```csharp
private System.Boolean <netsUpdated>k__BackingField;
```

- `private System.Boolean <lanesUpdated>k__BackingField`  

```csharp
private System.Boolean <lanesUpdated>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_NetGeometryQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetGeometryQuery;
```

- `private Unity.Entities.EntityQuery m_LaneGeometryQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneGeometryQuery;
```

- `private Game.Net.SearchSystem m_SearchSystem`  

```csharp
private Game.Net.SearchSystem m_SearchSystem;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedNetBounds`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedNetBounds;
```

- `private Unity.Jobs.JobHandle m_NetWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NetWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_NetReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NetReadDependencies;
```

- `private Unity.Jobs.JobHandle m_LaneWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_LaneWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_LaneReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_LaneReadDependencies;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedLaneBounds`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedLaneBounds;
```

- `private Game.Net.UpdateCollectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.UpdateCollectSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean netsUpdated { get; private set }`  

```csharp
public System.Boolean netsUpdated { get; private set; }
```

- `public System.Boolean lanesUpdated { get; private set }`  

```csharp
public System.Boolean lanesUpdated { get; private set; }
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

- `public AddLaneBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddLaneBoundsReader(Unity.Jobs.JobHandle handle);
```

- `public AddNetBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddNetBoundsReader(Unity.Jobs.JobHandle handle);
```

- `public GetUpdatedLaneBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedLaneBounds(Unity.Jobs.JobHandle& dependencies);
```

- `public GetUpdatedNetBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedNetBounds(Unity.Jobs.JobHandle& dependencies);
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

- `Game.Net.UpdateCollectSystem+CollectUpdatedNetBoundsJob`  
- `Game.Net.UpdateCollectSystem+CollectUpdatedLaneBoundsJob`  
- `Game.Net.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Net.UpdateCollectSystem+TypeHandle`  

