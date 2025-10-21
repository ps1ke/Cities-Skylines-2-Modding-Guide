# Game.Prefabs.StrictObjectBuiltRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StrictObjectBuiltRequirementSystem : Game.GameSystemBase
{
    private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Unity.Entities.EntityQuery m_ChangedQuery;
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private System.Boolean m_Loaded;
    private Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle __TypeHandle;

    public StrictObjectBuiltRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem`  

```csharp
private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Unity.Entities.EntityQuery m_ChangedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChangedQuery;
```

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public StrictObjectBuiltRequirementSystem()`  

```csharp
public StrictObjectBuiltRequirementSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Prefabs.StrictObjectBuiltRequirementSystem+TrackObjectsJob`  
- `Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle`  

