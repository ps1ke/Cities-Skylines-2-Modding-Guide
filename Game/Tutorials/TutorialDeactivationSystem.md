# Game.Tutorials.TutorialDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TutorialDeactivationSystem : Game.GameSystemBase
{
    private System.Collections.Generic.List<Game.Tutorials.TutorialDeactivationSystemBase> m_Systems;

    public TutorialDeactivationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Collections.Generic.List<Game.Tutorials.TutorialDeactivationSystemBase> m_Systems`  

```csharp
private System.Collections.Generic.List<Game.Tutorials.TutorialDeactivationSystemBase> m_Systems;
```


## Constructors

- `public TutorialDeactivationSystem()`  

```csharp
public TutorialDeactivationSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


