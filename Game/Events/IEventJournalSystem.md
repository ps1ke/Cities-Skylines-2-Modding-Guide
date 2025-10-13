# Game.Events.IEventJournalSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IEventJournalSystem
{
    public Unity.Collections.NativeList<Unity.Entities.Entity> eventJournal { get; }
    public System.Collections.Generic.IEnumerable<Game.Prefabs.JournalEventComponent> eventPrefabs { get; }
    public System.Action<Unity.Entities.Entity> eventEventDataChanged { get; set; }
    public System.Action eventEntryAdded { get; set; }

    public abstract Game.Events.EventJournalEntry GetInfo(Unity.Entities.Entity journalEntity);
    public abstract Unity.Entities.Entity GetPrefab(Unity.Entities.Entity journalEntity);
    public abstract System.Boolean TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data);
    public abstract System.Boolean TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data);
}
```


## Properties

- `public Unity.Collections.NativeList<Unity.Entities.Entity> eventJournal { get }`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> eventJournal { get; }
```

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.JournalEventComponent> eventPrefabs { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.JournalEventComponent> eventPrefabs { get; }
```

- `public System.Action<Unity.Entities.Entity> eventEventDataChanged { get; set }`  

```csharp
public System.Action<Unity.Entities.Entity> eventEventDataChanged { get; set; }
```

- `public System.Action eventEntryAdded { get; set }`  

```csharp
public System.Action eventEntryAdded { get; set; }
```


## Methods

- `public abstract GetInfo(Unity.Entities.Entity journalEntity) : Game.Events.EventJournalEntry`  

```csharp
public abstract Game.Events.EventJournalEntry GetInfo(Unity.Entities.Entity journalEntity);
```

- `public abstract GetPrefab(Unity.Entities.Entity journalEntity) : Unity.Entities.Entity`  

```csharp
public abstract Unity.Entities.Entity GetPrefab(Unity.Entities.Entity journalEntity);
```

- `public abstract TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data);
```

- `public abstract TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data);
```


