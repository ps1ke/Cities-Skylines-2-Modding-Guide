# Game.Tutorials.TutorialObjectSelectionDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialObjectSelectionDeactivationSystem : Game.Tutorials.TutorialDeactivationSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_PendingTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
    private Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle __TypeHandle;

    public TutorialObjectSelectionDeactivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CheckDeactivate(Unity.Entities.EntityQuery query, Unity.Entities.Entity selection, System.Boolean tool);
    private Unity.Entities.Entity GetSelection(System.Boolean& tool);
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

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
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

- `private Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialObjectSelectionDeactivationSystem()`  

```csharp
public TutorialObjectSelectionDeactivationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CheckDeactivate(Unity.Entities.EntityQuery query, Unity.Entities.Entity selection, System.Boolean tool) : System.Void`  

```csharp
private System.Void CheckDeactivate(Unity.Entities.EntityQuery query, Unity.Entities.Entity selection, System.Boolean tool);
```

- `private GetSelection(System.Boolean& tool) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetSelection(System.Boolean& tool);
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

- `Game.Tutorials.TutorialObjectSelectionDeactivationSystem+CheckTutorialsJob`  
- `Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle`  

