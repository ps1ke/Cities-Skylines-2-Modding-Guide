# Game.Tutorials.TutorialInfoviewDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialInfoviewDeactivationSystem : Game.Tutorials.TutorialDeactivationSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_PendingTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
    private Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle __TypeHandle;

    public TutorialInfoviewDeactivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CheckDeactivation(Unity.Entities.EntityQuery query);
    private Unity.Entities.Entity GetActiveInfoview();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_PendingTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
```

- `private Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialInfoviewDeactivationSystem()`  

```csharp
public TutorialInfoviewDeactivationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CheckDeactivation(Unity.Entities.EntityQuery query) : System.Void`  

```csharp
private System.Void CheckDeactivation(Unity.Entities.EntityQuery query);
```

- `private GetActiveInfoview() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetActiveInfoview();
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

- `Game.Tutorials.TutorialInfoviewDeactivationSystem+CheckDeactivationJob`  
- `Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle`  

