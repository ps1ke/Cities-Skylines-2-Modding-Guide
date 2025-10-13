# Game.Prefabs.SpectatorEventData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct SpectatorEventData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.EventTargetType m_RandomSiteType;
    public System.Single m_PreparationDuration;
    public System.Single m_ActiveDuration;
    public System.Single m_TerminationDuration;

}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomSiteType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomSiteType;
```

- `public System.Single m_PreparationDuration`  

```csharp
public System.Single m_PreparationDuration;
```

- `public System.Single m_ActiveDuration`  

```csharp
public System.Single m_ActiveDuration;
```

- `public System.Single m_TerminationDuration`  

```csharp
public System.Single m_TerminationDuration;
```


