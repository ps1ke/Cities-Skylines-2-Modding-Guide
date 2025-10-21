# Game.Prefabs.ZoneBuiltRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneBuiltRequirementSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedBuildingsQuery;
    private Unity.Entities.EntityQuery m_AllBuildingsQuery;
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Unity.Collections.NativeParallelHashMap<Game.Prefabs.ZoneBuiltDataKey, Game.Prefabs.ZoneBuiltDataValue> m_ZoneBuiltData;
    private Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> m_ZoneBuiltLevelQueue;
    private Unity.Jobs.JobHandle m_WriteDeps;
    private Unity.Jobs.JobHandle m_QueueWriteDeps;
    private System.Boolean m_Loaded;
    private Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle __TypeHandle;

    public ZoneBuiltRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Boolean GetLoaded();
    public Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> GetZoneBuiltLevelQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBuildingsQuery;
```

- `private Unity.Entities.EntityQuery m_AllBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllBuildingsQuery;
```

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Unity.Collections.NativeParallelHashMap<Game.Prefabs.ZoneBuiltDataKey, Game.Prefabs.ZoneBuiltDataValue> m_ZoneBuiltData`  

```csharp
private Unity.Collections.NativeParallelHashMap<Game.Prefabs.ZoneBuiltDataKey, Game.Prefabs.ZoneBuiltDataValue> m_ZoneBuiltData;
```

- `private Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> m_ZoneBuiltLevelQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> m_ZoneBuiltLevelQueue;
```

- `private Unity.Jobs.JobHandle m_WriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_WriteDeps;
```

- `private Unity.Jobs.JobHandle m_QueueWriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_QueueWriteDeps;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZoneBuiltRequirementSystem()`  

```csharp
public ZoneBuiltRequirementSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddWriter(Unity.Jobs.JobHandle jobHandle);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetZoneBuiltLevelQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate>`  

```csharp
public Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> GetZoneBuiltLevelQueue(Unity.Jobs.JobHandle& deps);
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

- `Game.Prefabs.ZoneBuiltRequirementSystem+ZoneBuiltData`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+UpdateZoneBuiltDataJob`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+ZoneBuiltRequirementJob`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle`  

