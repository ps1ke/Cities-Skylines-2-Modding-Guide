# Game.Tools.SelectionInfo

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct SelectionInfo : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Tools.SelectionType m_SelectionType;
    public Game.Areas.AreaType m_AreaType;

}
```


## Fields

- `public Game.Tools.SelectionType m_SelectionType`  

```csharp
public Game.Tools.SelectionType m_SelectionType;
```

- `public Game.Areas.AreaType m_AreaType`  

```csharp
public Game.Areas.AreaType m_AreaType;
```


