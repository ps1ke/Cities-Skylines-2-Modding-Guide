# Game.Prefabs.SeasonColorFilter

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SeasonColorFilter : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.SeasonColorFilter+ColorFilter[] m_ColorFilters;

    public SeasonColorFilter();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.SeasonColorFilter+ColorFilter[] m_ColorFilters`  

```csharp
public Game.Prefabs.SeasonColorFilter+ColorFilter[] m_ColorFilters;
```


## Constructors

- `public SeasonColorFilter()`  

```csharp
public SeasonColorFilter();
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
		for (int i = 0; i < m_ColorFilters.Length; i++)
		{
			SeasonPrefab seasonFilter = m_ColorFilters[i].m_SeasonFilter;
			if (seasonFilter != null)
			{
				prefabs.Add(seasonFilter);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Prefabs.ColorFilter>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		MeshColorSystem orCreateSystemManaged2 = entityManager.World.GetOrCreateSystemManaged<MeshColorSystem>();
		DynamicBuffer<Game.Prefabs.ColorFilter> buffer = entityManager.GetBuffer<Game.Prefabs.ColorFilter>(entity);
		int num = 0;
		for (int i = 0; i < m_ColorFilters.Length; i++)
		{
			num += m_ColorFilters[i].m_VariationGroups.Length;
		}
		buffer.ResizeUninitialized(num);
		num = 0;
		for (int j = 0; j < m_ColorFilters.Length; j++)
		{
			ColorFilter colorFilter = m_ColorFilters[j];
			Game.Prefabs.ColorFilter value = new Game.Prefabs.ColorFilter
			{
				m_AgeFilter = AgeMask.Any,
				m_GenderFilter = GenderMask.Any,
				m_OverrideProbability = (sbyte)math.clamp(colorFilter.m_OverrideProbability, -1, 100),
				m_OverrideAlpha = -1f
			};
			if (colorFilter.m_SeasonFilter != null)
			{
				value.m_EntityFilter = orCreateSystemManaged.GetEntity(colorFilter.m_SeasonFilter);
				value.m_Flags |= ColorFilterFlags.SeasonFilter;
			}
			for (int k = 0; k < colorFilter.m_VariationGroups.Length; k++)
			{
				value.m_GroupID = orCreateSystemManaged2.GetColorGroupID(colorFilter.m_VariationGroups[k]);
				buffer[num++] = value;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.SeasonColorFilter+ColorFilter`  

