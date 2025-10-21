# Game.Serialization.DataMigration.ShortLaneRemoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class ShortLaneRemoveSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_Query;

    public ShortLaneRemoveSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```


## Constructors

- `public ShortLaneRemoveSystem()`  

```csharp
public ShortLaneRemoveSystem();
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


