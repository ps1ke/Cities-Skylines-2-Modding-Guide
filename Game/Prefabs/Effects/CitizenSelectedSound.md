# Game.Prefabs.Effects.CitizenSelectedSound

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CitizenSelectedSound : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.Effects.CitizenSelectedSoundInfo[] m_CitizenSelectedSounds;

    public CitizenSelectedSound();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.Effects.CitizenSelectedSoundInfo[] m_CitizenSelectedSounds`  

```csharp
public Game.Prefabs.Effects.CitizenSelectedSoundInfo[] m_CitizenSelectedSounds;
```


## Constructors

- `public CitizenSelectedSound()`  

```csharp
public CitizenSelectedSound();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		for (int i = 0; i < m_CitizenSelectedSounds.Length; i++)
		{
			prefabs.Add(m_CitizenSelectedSounds[i].m_SelectedSound);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<CitizenSelectedSoundData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		if (m_CitizenSelectedSounds != null)
		{
			DynamicBuffer<CitizenSelectedSoundData> buffer = entityManager.GetBuffer<CitizenSelectedSoundData>(entity);
			for (int i = 0; i < m_CitizenSelectedSounds.Length; i++)
			{
				CitizenSelectedSoundInfo citizenSelectedSoundInfo = m_CitizenSelectedSounds[i];
				buffer.Add(new CitizenSelectedSoundData(citizenSelectedSoundInfo.m_IsSickOrInjured, citizenSelectedSoundInfo.m_Age, citizenSelectedSoundInfo.m_Happiness, orCreateSystemManaged.GetEntity(citizenSelectedSoundInfo.m_SelectedSound)));
			}
		}
	}
```


