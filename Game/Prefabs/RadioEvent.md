# Game.Prefabs.RadioEvent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RadioEvent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Audio.Radio.Radio+SegmentType m_SegmentType;
    public System.Int32 m_EmergencyFrameDelay;

    public RadioEvent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Audio.Radio.Radio+SegmentType m_SegmentType`  

```csharp
public Game.Audio.Radio.Radio+SegmentType m_SegmentType;
```

- `public System.Int32 m_EmergencyFrameDelay`  

```csharp
public System.Int32 m_EmergencyFrameDelay;
```


## Constructors

- `public RadioEvent()`  

```csharp
public RadioEvent();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Triggers.RadioEvent>());
		components.Add(ComponentType.ReadWrite<PrefabRef>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<RadioEventData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		List<ComponentBase> list = new List<ComponentBase>();
		GetComponents(list);
		HashSet<ComponentType> hashSet = new HashSet<ComponentType>();
		for (int i = 0; i < list.Count; i++)
		{
			list[i].GetArchetypeComponents(hashSet);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		RadioEventData componentData = default(RadioEventData);
		componentData.m_Archetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet));
		componentData.m_SegmentType = m_SegmentType;
		componentData.m_EmergencyFrameDelay = m_EmergencyFrameDelay;
		entityManager.SetComponentData(entity, componentData);
	}
```


