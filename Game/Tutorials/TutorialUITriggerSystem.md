# Game.Tutorials.TutorialUITriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUITriggerSystem`  

## Code

```csharp
public class TutorialUITriggerSystem : Game.Tutorials.TutorialTriggerSystemBase, Game.Tutorials.ITutorialUITriggerSystem
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private readonly System.Collections.Generic.HashSet<System.String> m_ActivatedTriggers;

    public TutorialUITriggerSystem();

    public System.Void ActivateTrigger(System.String trigger);
    public System.Void DisactivateTrigger(System.String trigger);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private readonly System.Collections.Generic.HashSet<System.String> m_ActivatedTriggers`  

```csharp
private readonly System.Collections.Generic.HashSet<System.String> m_ActivatedTriggers;
```


## Constructors

- `public TutorialUITriggerSystem()`  

```csharp
public TutorialUITriggerSystem();
```


## Methods

- `public ActivateTrigger(System.String trigger) : System.Void`  

```csharp
public System.Void ActivateTrigger(System.String trigger);
```

- `public DisactivateTrigger(System.String trigger) : System.Void`  

```csharp
public System.Void DisactivateTrigger(System.String trigger);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


