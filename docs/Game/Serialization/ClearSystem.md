# Game.Serialization.ClearSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class ClearSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ClearQuery;

    public ClearSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ClearQuery`  

```csharp
private Unity.Entities.EntityQuery m_ClearQuery;
```


## Constructors

- `public ClearSystem()`  

```csharp
public ClearSystem();
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


