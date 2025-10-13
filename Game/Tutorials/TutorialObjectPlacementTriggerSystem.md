# Game.Tutorials.TutorialObjectPlacementTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialObjectPlacementTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_CreatedObjectQuery;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Tutorials.TutorialObjectPlacementTriggerSystem+TypeHandle __TypeHandle;

    public TutorialObjectPlacementTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean HasElevation();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedObjectQuery;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Tutorials.TutorialObjectPlacementTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialObjectPlacementTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialObjectPlacementTriggerSystem()`  

```csharp
public TutorialObjectPlacementTriggerSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private HasElevation() : System.Boolean`  

```csharp
private System.Boolean HasElevation();
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

- `Game.Tutorials.TutorialObjectPlacementTriggerSystem+ClearCountJob`  
- `Game.Tutorials.TutorialObjectPlacementTriggerSystem+CheckObjectsJob`  
- `Game.Tutorials.TutorialObjectPlacementTriggerSystem+TypeHandle`  

