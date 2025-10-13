# Game.Prefabs.ResidentColorFilter

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ResidentColorFilter : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ResidentColorFilter+ColorFilter[] m_ColorFilters;

    public ResidentColorFilter();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ResidentColorFilter+ColorFilter[] m_ColorFilters`  

```csharp
public Game.Prefabs.ResidentColorFilter+ColorFilter[] m_ColorFilters;
```


## Constructors

- `public ResidentColorFilter()`  

```csharp
public ResidentColorFilter();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Prefabs.ColorFilter>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		MeshColorSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<MeshColorSystem>();
		DynamicBuffer<Game.Prefabs.ColorFilter> buffer = entityManager.GetBuffer<Game.Prefabs.ColorFilter>(entity);
		int num = 0;
		for (int i = 0; i < m_ColorFilters.Length; i++)
		{
			num += m_ColorFilters[i].m_VariationGroups.Length;
		}
		buffer.ResizeUninitialized(num);
		num = 0;
		ColorProperties component = GetComponent<ColorProperties>();
		for (int j = 0; j < m_ColorFilters.Length; j++)
		{
			ColorFilter colorFilter = m_ColorFilters[j];
			Game.Prefabs.ColorFilter value = new Game.Prefabs.ColorFilter
			{
				m_AgeFilter = colorFilter.m_AgeFilter,
				m_GenderFilter = colorFilter.m_GenderFilter,
				m_OverrideProbability = (sbyte)math.clamp(colorFilter.m_OverrideProbability, -1, 100),
				m_OverrideAlpha = -1f
			};
			if (component != null)
			{
				float3 alphas = math.select(math.saturate(colorFilter.m_OverrideAlpha), -1f, colorFilter.m_OverrideAlpha < 0f);
				value.m_OverrideAlpha.x = component.GetAlpha(alphas, 0, -1f);
				value.m_OverrideAlpha.y = component.GetAlpha(alphas, 1, -1f);
				value.m_OverrideAlpha.z = component.GetAlpha(alphas, 2, -1f);
			}
			for (int k = 0; k < colorFilter.m_VariationGroups.Length; k++)
			{
				value.m_GroupID = orCreateSystemManaged.GetColorGroupID(colorFilter.m_VariationGroups[k]);
				buffer[num++] = value;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.ResidentColorFilter+ColorFilter`  

