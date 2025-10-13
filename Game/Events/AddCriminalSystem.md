# Game.Events.AddCriminalSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AddCriminalSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_AddCriminalQuery;
    private Game.Events.AddCriminalSystem+TypeHandle __TypeHandle;

    public AddCriminalSystem();

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

- `private Unity.Entities.EntityQuery m_AddCriminalQuery`  

```csharp
private Unity.Entities.EntityQuery m_AddCriminalQuery;
```

- `private Game.Events.AddCriminalSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.AddCriminalSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AddCriminalSystem()`  

```csharp
public AddCriminalSystem();
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

- `Game.Events.AddCriminalSystem+AddCriminalJob`  
- `Game.Events.AddCriminalSystem+TypeHandle`  

