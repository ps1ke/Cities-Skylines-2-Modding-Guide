# Game.Prefabs.DistrictModifiers

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DistrictModifiers : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.DistrictModifierInfo[] m_Modifiers;

    public DistrictModifiers();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.DistrictModifierInfo[] m_Modifiers`  

```csharp
public Game.Prefabs.DistrictModifierInfo[] m_Modifiers;
```


## Constructors

- `public DistrictModifiers()`  

```csharp
public DistrictModifiers();
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
		components.Add(ComponentType.ReadWrite<DistrictModifierData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		if (m_Modifiers != null)
		{
			DynamicBuffer<DistrictModifierData> buffer = entityManager.GetBuffer<DistrictModifierData>(entity);
			for (int i = 0; i < m_Modifiers.Length; i++)
			{
				DistrictModifierInfo districtModifierInfo = m_Modifiers[i];
				buffer.Add(new DistrictModifierData(districtModifierInfo.m_Type, districtModifierInfo.m_Mode, districtModifierInfo.m_Range));
			}
		}
	}
```


