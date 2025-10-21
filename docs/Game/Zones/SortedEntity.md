# Game.Zones.CellCheckHelpers+SortedEntity

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Zones.CellCheckHelpers+SortedEntity>`  

## Code

```csharp
public sealed struct SortedEntity : System.IComparable<Game.Zones.CellCheckHelpers+SortedEntity>
{
    public Unity.Entities.Entity m_Entity;

    public System.Int32 CompareTo(Game.Zones.CellCheckHelpers+SortedEntity other);
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```


## Methods

- `public CompareTo(Game.Zones.CellCheckHelpers+SortedEntity other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Zones.CellCheckHelpers+SortedEntity other);
```


