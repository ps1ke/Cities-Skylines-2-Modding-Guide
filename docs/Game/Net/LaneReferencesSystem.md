# Game.Net.LaneReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneReferencesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_LanesQuery;
    private Unity.Entities.EntityQuery m_UpdatedOwnersQuery;
    private Unity.Entities.EntityQuery m_AllOwnersQuery;
    private Unity.Collections.NativeQueue<Game.Net.Lane> m_SkipLaneQueue;
    private Unity.Jobs.JobHandle m_SkipLaneDeps;
    private System.Boolean m_Loaded;
    private Game.Net.LaneReferencesSystem+TypeHandle __TypeHandle;

    public LaneReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSkipLaneWriter(Unity.Jobs.JobHandle dependency);
    private System.Boolean GetLoaded();
    public Unity.Collections.NativeQueue<Game.Net.Lane> GetSkipLaneQueue();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_LanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_LanesQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedOwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedOwnersQuery;
```

- `private Unity.Entities.EntityQuery m_AllOwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllOwnersQuery;
```

- `private Unity.Collections.NativeQueue<Game.Net.Lane> m_SkipLaneQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Net.Lane> m_SkipLaneQueue;
```

- `private Unity.Jobs.JobHandle m_SkipLaneDeps`  

```csharp
private Unity.Jobs.JobHandle m_SkipLaneDeps;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.LaneReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneReferencesSystem()`  

```csharp
public LaneReferencesSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddSkipLaneWriter(Unity.Jobs.JobHandle dependency) : System.Void`  

```csharp
public System.Void AddSkipLaneWriter(Unity.Jobs.JobHandle dependency);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetSkipLaneQueue() : Unity.Collections.NativeQueue<Game.Net.Lane>`  

```csharp
public Unity.Collections.NativeQueue<Game.Net.Lane> GetSkipLaneQueue();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Net.LaneReferencesSystem+UpdateLaneReferencesJob`  
- `Game.Net.LaneReferencesSystem+FillNodeMapJob`  
- `Game.Net.LaneReferencesSystem+FixSkippedLanesJob`  
- `Game.Net.LaneReferencesSystem+UpdateLaneIndicesJob`  
- `Game.Net.LaneReferencesSystem+SubLaneOrder`  
- `Game.Net.LaneReferencesSystem+TypeHandle`  

