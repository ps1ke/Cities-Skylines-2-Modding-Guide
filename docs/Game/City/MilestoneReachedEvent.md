# Game.City.MilestoneReachedEvent

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct MilestoneReachedEvent : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Milestone;
    public System.Int32 m_Index;

    public MilestoneReachedEvent(Unity.Entities.Entity milestone, System.Int32 index);

}
```


## Fields

- `public Unity.Entities.Entity m_Milestone`  

```csharp
public Unity.Entities.Entity m_Milestone;
```

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```


## Constructors

- `public MilestoneReachedEvent(Unity.Entities.Entity milestone, System.Int32 index)`  

```csharp
public MilestoneReachedEvent(Unity.Entities.Entity milestone, System.Int32 index);
```


