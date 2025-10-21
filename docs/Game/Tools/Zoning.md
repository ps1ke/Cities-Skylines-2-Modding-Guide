# Game.Tools.Zoning

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Zoning : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Colossal.Mathematics.Quad3 m_Position;
    public Game.Tools.ZoningFlags m_Flags;

}
```


## Fields

- `public Colossal.Mathematics.Quad3 m_Position`  

```csharp
public Colossal.Mathematics.Quad3 m_Position;
```

- `public Game.Tools.ZoningFlags m_Flags`  

```csharp
public Game.Tools.ZoningFlags m_Flags;
```


