# Game.UI.InGame.EventJournalUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Events.IEventJournalSystem m_EventJournalSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_EventMap`  
- `private Colossal.UI.Binding.RawValueBinding m_Events`  
- `private System.Action <eventJournalOpened>k__BackingField`  
- `private System.Action <eventJournalClosed>k__BackingField`  
- `private static const System.String kGroup`  
- `private static const System.Int32 kMaxMessages`  

## Properties

- `public System.Action eventJournalOpened { get; set }`  
- `public System.Action eventJournalClosed { get; set }`  

## Constructors

- `public EventJournalUISystem()`  

## Methods

- `private <OnCreate>b__15_0() : System.Void`  
- `private <OnCreate>b__15_1() : System.Void`  
- `private <OnCreate>b__15_2(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  
- `private BindEvents(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindJournalEntry(Unity.Entities.Entity entity, Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `private OnEntryAdded() : System.Void`  
- `private OnEventDataChanged(Unity.Entities.Entity entity) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

