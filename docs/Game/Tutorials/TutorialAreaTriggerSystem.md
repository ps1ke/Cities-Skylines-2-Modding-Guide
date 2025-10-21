# Game.Tutorials.TutorialAreaTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialAreaTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Unity.Entities.EntityQuery m_AreaModificationQuery;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Tutorials.TutorialAreaTriggerSystem+TypeHandle __TypeHandle;

    public TutorialAreaTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AreaModificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaModificationQuery;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Tutorials.TutorialAreaTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialAreaTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialAreaTriggerSystem()`  

```csharp
public TutorialAreaTriggerSystem();
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

- `Game.Tutorials.TutorialAreaTriggerSystem+CheckModifiedAreasJob`  
- `Game.Tutorials.TutorialAreaTriggerSystem+TypeHandle`  

