# Game.Events.IEventJournalSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** interface abstract public  


## Properties

- `public Unity.Collections.NativeList<Unity.Entities.Entity> eventJournal { get }`  
- `public System.Collections.Generic.IEnumerable<Game.Prefabs.JournalEventComponent> eventPrefabs { get }`  
- `public System.Action<Unity.Entities.Entity> eventEventDataChanged { get; set }`  
- `public System.Action eventEntryAdded { get; set }`  

## Methods

- `public abstract GetInfo(Unity.Entities.Entity journalEntity) : Game.Events.EventJournalEntry`  
- `public abstract GetPrefab(Unity.Entities.Entity journalEntity) : Unity.Entities.Entity`  
- `public abstract TryGetCityEffects(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalCityEffect, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  
- `public abstract TryGetData(Unity.Entities.Entity journalEntity, Unity.Entities.DynamicBuffer`1[[Game.Events.EventJournalData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& data) : System.Boolean`  

