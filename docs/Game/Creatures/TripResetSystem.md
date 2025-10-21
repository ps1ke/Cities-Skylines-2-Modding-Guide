# Game.Creatures.TripResetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TripResetSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ResetQuery;
    private Game.Creatures.TripResetSystem+TypeHandle __TypeHandle;

    public TripResetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ResetQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResetQuery;
```

- `private Game.Creatures.TripResetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Creatures.TripResetSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TripResetSystem()`  

```csharp
public TripResetSystem();
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

- `Game.Creatures.TripResetSystem+CreatureTripResetJob`  
- `Game.Creatures.TripResetSystem+TypeHandle`  

