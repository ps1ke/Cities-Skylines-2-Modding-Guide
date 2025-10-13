# Game.Prefabs.AudioGroupingSettingsPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AudioGroupingSettingsPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.AudioGroupSettings[] m_Settings;

    public AudioGroupingSettingsPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.AudioGroupSettings[] m_Settings`  

```csharp
public Game.Prefabs.AudioGroupSettings[] m_Settings;
```


## Constructors

- `public AudioGroupingSettingsPrefab()`  

```csharp
public AudioGroupingSettingsPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		if (m_Settings != null)
		{
			for (int i = 0; i < m_Settings.Length; i++)
			{
				if (m_Settings[i].m_GroupSoundFar != null)
				{
					prefabs.Add(m_Settings[i].m_GroupSoundFar);
				}
				if (m_Settings[i].m_GroupSoundNear != null)
				{
					prefabs.Add(m_Settings[i].m_GroupSoundNear);
				}
			}
		}
		base.GetDependencies(prefabs);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<AudioGroupingSettingsData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		DynamicBuffer<AudioGroupingSettingsData> buffer = entityManager.GetBuffer<AudioGroupingSettingsData>(entity);
		if (m_Settings != null)
		{
			for (int i = 0; i < m_Settings.Length; i++)
			{
				AudioGroupSettings audioGroupSettings = m_Settings[i];
				buffer.Add(new AudioGroupingSettingsData
				{
					m_Type = audioGroupSettings.m_Type,
					m_FadeSpeed = audioGroupSettings.m_FadeSpeed,
					m_Scale = audioGroupSettings.m_Scale,
					m_GroupSoundFar = orCreateSystemManaged.GetEntity(audioGroupSettings.m_GroupSoundFar),
					m_GroupSoundNear = ((audioGroupSettings.m_GroupSoundNear != null) ? orCreateSystemManaged.GetEntity(audioGroupSettings.m_GroupSoundNear) : Entity.Null),
					m_Height = audioGroupSettings.m_Height,
					m_NearHeight = audioGroupSettings.m_NearHeight,
					m_NearWeight = audioGroupSettings.m_NearWeight
				});
			}
		}
	}
```


