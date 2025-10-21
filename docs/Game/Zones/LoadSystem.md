# Game.Zones.LoadSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class LoadSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_EntityQuery;

    public LoadSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_EntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_EntityQuery;
```


## Constructors

- `public LoadSystem()`  

```csharp
public LoadSystem();
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


