# Game.Common.RaycastResult

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.IAccumulable<Game.Common.RaycastResult>`  

## Code

```csharp
public sealed struct RaycastResult : Colossal.Collections.IAccumulable<Game.Common.RaycastResult>
{
    public Game.Common.RaycastHit m_Hit;
    public Unity.Entities.Entity m_Owner;

    public System.Void Accumulate(Game.Common.RaycastResult other);
}
```


## Fields

- `public Game.Common.RaycastHit m_Hit`  

```csharp
public Game.Common.RaycastHit m_Hit;
```

- `public Unity.Entities.Entity m_Owner`  

```csharp
public Unity.Entities.Entity m_Owner;
```


## Methods

- `public Accumulate(Game.Common.RaycastResult other) : System.Void`  

```csharp
public System.Void Accumulate(Game.Common.RaycastResult other);
```


