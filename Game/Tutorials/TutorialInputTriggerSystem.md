# Game.Tutorials.TutorialInputTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

## Code

```csharp
public class TutorialInputTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;

    public TutorialInputTriggerSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Boolean Performed(Game.Prefabs.TutorialInputTriggerPrefab prefab);
}
```


## Fields

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```


## Constructors

- `public TutorialInputTriggerSystem()`  

```csharp
public TutorialInputTriggerSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private Performed(Game.Prefabs.TutorialInputTriggerPrefab prefab) : System.Boolean`  

```csharp
private System.Boolean Performed(Game.Prefabs.TutorialInputTriggerPrefab prefab);
```


