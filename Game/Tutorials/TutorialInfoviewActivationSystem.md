# Game.Tutorials.TutorialInfoviewActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialInfoviewActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_TutorialQuery;
    private Game.Tutorials.TutorialInfoviewActivationSystem+TypeHandle __TypeHandle;

    public TutorialInfoviewActivationSystem();

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

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```

- `private Game.Tutorials.TutorialInfoviewActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialInfoviewActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialInfoviewActivationSystem()`  

```csharp
public TutorialInfoviewActivationSystem();
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

- `Game.Tutorials.TutorialInfoviewActivationSystem+CheckActivationJob`  
- `Game.Tutorials.TutorialInfoviewActivationSystem+TypeHandle`  

