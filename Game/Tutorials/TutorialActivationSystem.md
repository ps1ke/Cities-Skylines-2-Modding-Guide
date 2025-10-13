# Game.Tutorials.TutorialActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TutorialActivationSystem : Game.GameSystemBase
{
    private readonly System.Collections.Generic.List<Game.GameSystemBase> m_Systems;

    public TutorialActivationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private readonly System.Collections.Generic.List<Game.GameSystemBase> m_Systems`  

```csharp
private readonly System.Collections.Generic.List<Game.GameSystemBase> m_Systems;
```


## Constructors

- `public TutorialActivationSystem()`  

```csharp
public TutorialActivationSystem();
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


