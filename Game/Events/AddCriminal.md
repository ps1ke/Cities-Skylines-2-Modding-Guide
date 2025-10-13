# Game.Events.AddCriminal

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct AddCriminal : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_Target;
    public Game.Citizens.CriminalFlags m_Flags;

}
```


## Fields

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Game.Citizens.CriminalFlags m_Flags`  

```csharp
public Game.Citizens.CriminalFlags m_Flags;
```


