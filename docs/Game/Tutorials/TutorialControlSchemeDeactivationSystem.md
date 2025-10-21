# Game.Tutorials.TutorialControlSchemeDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialControlSchemeDeactivationSystem : Game.Tutorials.TutorialDeactivationSystemBase
{
    private Unity.Entities.EntityQuery m_PendingTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
    private Game.Tutorials.TutorialControlSchemeDeactivationSystem+TypeHandle __TypeHandle;

    public TutorialControlSchemeDeactivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CheckDeactivate(Unity.Entities.EntityQuery query);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_PendingTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
```

- `private Game.Tutorials.TutorialControlSchemeDeactivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialControlSchemeDeactivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialControlSchemeDeactivationSystem()`  

```csharp
public TutorialControlSchemeDeactivationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CheckDeactivate(Unity.Entities.EntityQuery query) : System.Void`  

```csharp
private System.Void CheckDeactivate(Unity.Entities.EntityQuery query);
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

- `Game.Tutorials.TutorialControlSchemeDeactivationSystem+DeactivateJob`  
- `Game.Tutorials.TutorialControlSchemeDeactivationSystem+TypeHandle`  

