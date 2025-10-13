# Game.Prefabs.PrefabUnlockedRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabUnlockedRequirementSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Unity.Entities.EntityQuery m_UnlockQuery;
    private Unity.Entities.EntityQuery m_PrefabUnlockedQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Prefabs.PrefabUnlockedRequirementSystem+TypeHandle __TypeHandle;

    public PrefabUnlockedRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Unity.Entities.EntityQuery m_UnlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabUnlockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabUnlockedQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Prefabs.PrefabUnlockedRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.PrefabUnlockedRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PrefabUnlockedRequirementSystem()`  

```csharp
public PrefabUnlockedRequirementSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Prefabs.PrefabUnlockedRequirementSystem+UnlockJob`  
- `Game.Prefabs.PrefabUnlockedRequirementSystem+TypeHandle`  

