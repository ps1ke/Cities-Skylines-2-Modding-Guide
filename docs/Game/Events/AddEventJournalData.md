# Game.Events.AddEventJournalData

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct AddEventJournalData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Events.EventDataTrackingType m_Type;
    public Unity.Entities.Entity m_Event;
    public System.Int32 m_Count;

    public AddEventJournalData(Unity.Entities.Entity eventEntity, Game.Events.EventDataTrackingType type, System.Int32 count);

}
```


## Fields

- `public Game.Events.EventDataTrackingType m_Type`  

```csharp
public Game.Events.EventDataTrackingType m_Type;
```

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public System.Int32 m_Count`  

```csharp
public System.Int32 m_Count;
```


## Constructors

- `public AddEventJournalData(Unity.Entities.Entity eventEntity, Game.Events.EventDataTrackingType type, System.Int32 count = 1)`  

```csharp
public AddEventJournalData(Unity.Entities.Entity eventEntity, Game.Events.EventDataTrackingType type, System.Int32 count);
```


