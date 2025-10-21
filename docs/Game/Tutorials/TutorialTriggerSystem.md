# Game.Tutorials.TutorialTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class TutorialTriggerSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private readonly System.Collections.Generic.List<Game.Tutorials.TutorialTriggerSystemBase> m_Systems;
    private Unity.Entities.EntityQuery m_TriggerQuery;

    public TutorialTriggerSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private readonly System.Collections.Generic.List<Game.Tutorials.TutorialTriggerSystemBase> m_Systems`  

```csharp
private readonly System.Collections.Generic.List<Game.Tutorials.TutorialTriggerSystemBase> m_Systems;
```

- `private Unity.Entities.EntityQuery m_TriggerQuery`  

```csharp
private Unity.Entities.EntityQuery m_TriggerQuery;
```


## Constructors

- `public TutorialTriggerSystem()`  

```csharp
public TutorialTriggerSystem();
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

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


