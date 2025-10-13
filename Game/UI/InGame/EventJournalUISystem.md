# Game.UI.InGame.EventJournalUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventJournalUISystem : Game.UI.UISystemBase
{
    private Game.Events.IEventJournalSystem m_EventJournalSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_EventMap;
    private Colossal.UI.Binding.RawValueBinding m_Events;
    private System.Action <eventJournalOpened>k__BackingField;
    private System.Action <eventJournalClosed>k__BackingField;
    private static const System.String kGroup;
    private static const System.Int32 kMaxMessages;

    public System.Action eventJournalOpened { get; set; }
    public System.Action eventJournalClosed { get; set; }

    public EventJournalUISystem();

    private System.Void <OnCreate>b__15_0();
    private System.Void <OnCreate>b__15_1();
    private System.Void <OnCreate>b__15_2(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.Void BindEvents(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindJournalEntry(Unity.Entities.Entity entity, Colossal.UI.Binding.IJsonWriter binder);
    protected virtual System.Void OnCreate();
    private System.Void OnEntryAdded();
    private System.Void OnEventDataChanged(Unity.Entities.Entity entity);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Events.IEventJournalSystem m_EventJournalSystem`  

```csharp
private Game.Events.IEventJournalSystem m_EventJournalSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_EventMap`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_EventMap;
```

- `private Colossal.UI.Binding.RawValueBinding m_Events`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_Events;
```

- `private System.Action <eventJournalOpened>k__BackingField`  

```csharp
private System.Action <eventJournalOpened>k__BackingField;
```

- `private System.Action <eventJournalClosed>k__BackingField`  

```csharp
private System.Action <eventJournalClosed>k__BackingField;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.Int32 kMaxMessages`  

```csharp
private static const System.Int32 kMaxMessages;
```


## Properties

- `public System.Action eventJournalOpened { get; set }`  

```csharp
public System.Action eventJournalOpened { get; set; }
```

- `public System.Action eventJournalClosed { get; set }`  

```csharp
public System.Action eventJournalClosed { get; set; }
```


## Constructors

- `public EventJournalUISystem()`  

```csharp
[Preserve]
	public EventJournalUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__15_0() : System.Void`  

```csharp
private System.Void <OnCreate>b__15_0();
```

- `private <OnCreate>b__15_1() : System.Void`  

```csharp
private System.Void <OnCreate>b__15_1();
```

- `private <OnCreate>b__15_2(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void <OnCreate>b__15_2(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
```

- `private BindEvents(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindEvents(IJsonWriter binder)
	{
		binder.ArrayBegin(Math.Min(m_EventJournalSystem.eventJournal.Length, 100));
		int num = m_EventJournalSystem.eventJournal.Length - 1;
		while (num >= 0 && num >= m_EventJournalSystem.eventJournal.Length - 100)
		{
			binder.Write(m_EventJournalSystem.eventJournal[num]);
			num--;
		}
		binder.ArrayEnd();
	}
```

- `private BindJournalEntry(Unity.Entities.Entity entity, Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindJournalEntry(Entity entity, IJsonWriter binder)
	{
		EventJournalEntry info = m_EventJournalSystem.GetInfo(entity);
		Entity prefab = m_EventJournalSystem.GetPrefab(entity);
		EventPrefab prefab2 = m_PrefabSystem.GetPrefab<EventPrefab>(prefab);
		JournalEventComponent component = prefab2.GetComponent<JournalEventComponent>();
		binder.TypeBegin("eventJournal.EventInfo");
		binder.PropertyName("id");
		binder.Write(prefab2.name);
		binder.PropertyName("icon");
		binder.Write(component.m_Icon);
		binder.PropertyName("date");
		binder.Write(info.m_StartFrame - TimeData.GetSingleton(m_TimeDataQuery).m_FirstFrame);
		binder.PropertyName("data");
		if (m_EventJournalSystem.TryGetData(entity, out var data))
		{
			binder.ArrayBegin(data.Length);
			for (int i = 0; i < data.Length; i++)
			{
				binder.TypeBegin("eventJournal.UIEventData");
				binder.PropertyName("type");
				binder.Write(Enum.GetName(typeof(EventDataTrackingType), data[i].m_Type));
				binder.PropertyName("value");
				binder.Write(data[i].m_Value);
				binder.TypeEnd();
			}
			binder.ArrayEnd();
		}
		else
		{
			binder.WriteNull();
		}
		binder.PropertyName("effects");
		if (m_EventJournalSystem.TryGetCityEffects(entity, out var data2))
		{
			binder.ArrayBegin(data2.Length);
			for (int j = 0; j < data2.Length; j++)
			{
				binder.TypeBegin("eventJournal.UIEventData");
				binder.PropertyName("type");
				binder.Write(Enum.GetName(typeof(EventCityEffectTrackingType), data2[j].m_Type));
				binder.PropertyName("value");
				binder.Write(EventJournalUtils.GetPercentileChange(data2[j]));
				binder.TypeEnd();
			}
			binder.ArrayEnd();
		}
		else
		{
			binder.WriteNull();
		}
		binder.TypeEnd();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_EventJournalSystem = base.World.GetOrCreateSystemManaged<EventJournalSystem>();
		IEventJournalSystem eventJournalSystem = m_EventJournalSystem;
		eventJournalSystem.eventEventDataChanged = (Action<Entity>)Delegate.Combine(eventJournalSystem.eventEventDataChanged, new Action<Entity>(OnEventDataChanged));
		IEventJournalSystem eventJournalSystem2 = m_EventJournalSystem;
		eventJournalSystem2.eventEntryAdded = (Action)Delegate.Combine(eventJournalSystem2.eventEntryAdded, new Action(OnEntryAdded));
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		AddBinding(new TriggerBinding("eventJournal", "openJournal", delegate
		{
			eventJournalOpened?.Invoke();
		}));
		AddBinding(new TriggerBinding("eventJournal", "closeJournal", delegate
		{
			eventJournalClosed?.Invoke();
		}));
		AddBinding(m_Events = new RawValueBinding("eventJournal", "events", BindEvents));
		AddBinding(m_EventMap = new RawMapBinding<Entity>("eventJournal", "eventMap", delegate(IJsonWriter binder, Entity entity)
		{
			BindJournalEntry(entity, binder);
		}));
	}
```

- `private OnEntryAdded() : System.Void`  

```csharp
private void OnEntryAdded()
	{
		m_Events.Update();
	}
```

- `private OnEventDataChanged(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnEventDataChanged(Entity entity)
	{
		m_EventMap.Update(entity);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
	}
```


