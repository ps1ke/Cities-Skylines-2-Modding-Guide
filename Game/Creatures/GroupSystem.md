# Game.Creatures.GroupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GroupSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Game.Creatures.GroupSystem+TypeHandle __TypeHandle;

    public GroupSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Game.Creatures.GroupSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Creatures.GroupSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GroupSystem()`  

```csharp
public GroupSystem();
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

- `Game.Creatures.GroupSystem+GroupData`  
- `Game.Creatures.GroupSystem+ResetTripSetJob`  
- `Game.Creatures.GroupSystem+FillGroupQueueJob`  
- `Game.Creatures.GroupSystem+GroupCreaturesJob`  
- `Game.Creatures.GroupSystem+TypeHandle`  

