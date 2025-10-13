# Game.UI.InGame.UpgradeMenuUISystem+SortableEntity

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity>`  

## Code

```csharp
public sealed struct SortableEntity : System.IComparable<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity>
{
    public Unity.Entities.Entity m_Entity;
    public System.Int32 m_Priority;

    public System.Int32 CompareTo(Game.UI.InGame.UpgradeMenuUISystem+SortableEntity other);
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```


## Methods

- `public CompareTo(Game.UI.InGame.UpgradeMenuUISystem+SortableEntity other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.UpgradeMenuUISystem+SortableEntity other);
```


