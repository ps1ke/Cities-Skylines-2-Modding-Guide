# Game.Prefabs.JournalEventComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class JournalEventComponent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.String m_Icon;
    public Game.Events.EventDataTrackingType[] m_TrackedData;
    public Game.Events.EventCityEffectTrackingType[] m_TrackedCityEffects;

    public JournalEventComponent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Int32 GetDataFlags();
    public System.Int32 GetEffectFlags();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.String m_Icon`  

```csharp
public System.String m_Icon;
```

- `public Game.Events.EventDataTrackingType[] m_TrackedData`  

```csharp
public Game.Events.EventDataTrackingType[] m_TrackedData;
```

- `public Game.Events.EventCityEffectTrackingType[] m_TrackedCityEffects`  

```csharp
public Game.Events.EventCityEffectTrackingType[] m_TrackedCityEffects;
```


## Constructors

- `public JournalEventComponent()`  

```csharp
public JournalEventComponent();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<JournalEvent>());
	}
```

- `public GetDataFlags() : System.Int32`  

```csharp
public int GetDataFlags()
	{
		int num = 0;
		for (int i = 0; i < m_TrackedData.Length; i++)
		{
			if (EventJournalUtils.IsValid(m_TrackedData[i]))
			{
				num |= 1 << (int)m_TrackedData[i];
			}
		}
		return num;
	}
```

- `public GetEffectFlags() : System.Int32`  

```csharp
public int GetEffectFlags()
	{
		int num = 0;
		for (int i = 0; i < m_TrackedCityEffects.Length; i++)
		{
			if (EventJournalUtils.IsValid(m_TrackedCityEffects[i]))
			{
				num |= 1 << (int)m_TrackedCityEffects[i];
			}
		}
		return num;
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<JournalEventPrefabData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new JournalEventPrefabData
		{
			m_DataFlags = GetDataFlags(),
			m_EffectFlags = GetEffectFlags()
		});
	}
```


