# Game.Tutorials.TutorialUIDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUIDeactivationSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialUIDeactivationSystem : Game.Tutorials.TutorialDeactivationSystemBase, Game.Tutorials.ITutorialUIDeactivationSystem
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private readonly System.Collections.Generic.HashSet<System.String> m_Deactivate;
    private Unity.Entities.EntityQuery m_PendingTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialQuery;

    public TutorialUIDeactivationSystem();

    private System.Void CheckDeactivate(Unity.Entities.EntityQuery query);
    public System.Void DeactivateTag(System.String tag);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private readonly System.Collections.Generic.HashSet<System.String> m_Deactivate`  

```csharp
private readonly System.Collections.Generic.HashSet<System.String> m_Deactivate;
```

- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_PendingTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
```


## Constructors

- `public TutorialUIDeactivationSystem()`  

```csharp
public TutorialUIDeactivationSystem();
```


## Methods

- `private CheckDeactivate(Unity.Entities.EntityQuery query) : System.Void`  

```csharp
private System.Void CheckDeactivate(Unity.Entities.EntityQuery query);
```

- `public DeactivateTag(System.String tag) : System.Void`  

```csharp
public System.Void DeactivateTag(System.String tag);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


