# Game.Tutorials.TutorialObjectSelectionTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialObjectSelectionTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Unity.Entities.Entity m_LastSelection;
    private Game.Tutorials.TutorialObjectSelectionTriggerSystem+TypeHandle __TypeHandle;

    public TutorialObjectSelectionTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Unity.Entities.Entity m_LastSelection`  

```csharp
private Unity.Entities.Entity m_LastSelection;
```

- `private Game.Tutorials.TutorialObjectSelectionTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialObjectSelectionTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialObjectSelectionTriggerSystem()`  

```csharp
public TutorialObjectSelectionTriggerSystem();
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

- `Game.Tutorials.TutorialObjectSelectionTriggerSystem+CheckSelectionJob`  
- `Game.Tutorials.TutorialObjectSelectionTriggerSystem+TypeHandle`  

