# Game.Common.NativeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class NativeSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_EntityQuery;
    private Unity.Entities.EntityQuery m_NativeQuery;

    public NativeSystem();

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

- `private Unity.Entities.EntityQuery m_NativeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NativeQuery;
```


## Constructors

- `public NativeSystem()`  

```csharp
public NativeSystem();
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


