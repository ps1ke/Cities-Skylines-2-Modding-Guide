# Game.Tutorials.TutorialObjectSelectedActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialObjectSelectedActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.RouteToolSystem m_RouteToolSystem;
    private Unity.Entities.EntityQuery m_TutorialQuery;
    private Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle __TypeHandle;

    public TutorialObjectSelectedActivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Entities.Entity GetSelection(System.Boolean& tool);
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

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  

```csharp
private Game.Tools.RouteToolSystem m_RouteToolSystem;
```

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```

- `private Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialObjectSelectedActivationSystem()`  

```csharp
public TutorialObjectSelectedActivationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Tutorials.TutorialObjectSelectedActivationSystem+ActivateJob`  
- `Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle`  

