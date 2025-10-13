# Game.Prefabs.Effects.AudioRandomize

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AudioRandomize : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EffectPrefab[] m_SFXes;

    public AudioRandomize();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EffectPrefab[] m_SFXes`  

```csharp
public Game.Prefabs.EffectPrefab[] m_SFXes;
```


## Constructors

- `public AudioRandomize()`  

```csharp
public AudioRandomize();
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
		if (m_SFXes != null)
		{
			EffectPrefab[] sFXes = m_SFXes;
			foreach (EffectPrefab item in sFXes)
			{
				prefabs.Add(item);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<AudioRandomizeData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		if (m_SFXes != null)
		{
			for (int i = 0; i < m_SFXes.Length; i++)
			{
				bool flag = false;
				for (int j = 0; j < m_SFXes[i].components.Count; j++)
				{
					ComponentBase componentBase = m_SFXes[i].components[j];
					if (componentBase is SFX)
					{
						flag = true;
						if (((SFX)componentBase).m_Loop)
						{
							string p = orCreateSystemManaged.GetPrefab<EffectPrefab>(entity).name;
							ComponentBase.baseLog.WarnFormat("Warning: AudioRandomize {0} SFX {1} is looping", p, j);
						}
					}
				}
				if (!flag)
				{
					ComponentBase.baseLog.WarnFormat("Warning: AudioRandomize {0} has SFX without SFX component", base.name);
				}
			}
			DynamicBuffer<AudioRandomizeData> buffer = entityManager.GetBuffer<AudioRandomizeData>(entity);
			buffer.ResizeUninitialized(m_SFXes.Length);
			for (int k = 0; k < m_SFXes.Length; k++)
			{
				buffer[k] = new AudioRandomizeData
				{
					m_SFXEntity = orCreateSystemManaged.GetEntity(m_SFXes[k])
				};
			}
		}
		else
		{
			ComponentBase.baseLog.WarnFormat("Warning: AudioRandomize {0} has no sound effects", base.name);
		}
	}
```


