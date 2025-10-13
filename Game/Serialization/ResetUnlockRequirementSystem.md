# Game.Serialization.ResetUnlockRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResetUnlockRequirementSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Game.Serialization.ResetUnlockRequirementSystem+TypeHandle __TypeHandle;

    public ResetUnlockRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Game.Serialization.ResetUnlockRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ResetUnlockRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResetUnlockRequirementSystem()`  

```csharp
public ResetUnlockRequirementSystem();
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

- `Game.Serialization.ResetUnlockRequirementSystem+ResetUnlockRequirementJob`  
- `Game.Serialization.ResetUnlockRequirementSystem+TypeHandle`  

