# Game.Tutorials.TutorialAutoActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialAutoActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Unity.Entities.EntityQuery m_AutoActivateQuery;
    private Game.Tutorials.TutorialAutoActivationSystem+TypeHandle __TypeHandle;

    public TutorialAutoActivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private Unity.Entities.EntityQuery m_AutoActivateQuery`  

```csharp
private Unity.Entities.EntityQuery m_AutoActivateQuery;
```

- `private Game.Tutorials.TutorialAutoActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialAutoActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialAutoActivationSystem()`  

```csharp
public TutorialAutoActivationSystem();
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

- `Game.Tutorials.TutorialAutoActivationSystem+ActivateJob`  
- `Game.Tutorials.TutorialAutoActivationSystem+TypeHandle`  

