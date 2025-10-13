# Game.Prefabs.BuildingModifiers

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingModifiers : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.BuildingModifierInfo[] m_Modifiers;

    public BuildingModifiers();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.BuildingModifierInfo[] m_Modifiers`  

```csharp
public Game.Prefabs.BuildingModifierInfo[] m_Modifiers;
```


## Constructors

- `public BuildingModifiers()`  

```csharp
public BuildingModifiers();
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
		components.Add(ComponentType.ReadWrite<BuildingModifierData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		if (m_Modifiers != null)
		{
			DynamicBuffer<BuildingModifierData> buffer = entityManager.GetBuffer<BuildingModifierData>(entity);
			for (int i = 0; i < m_Modifiers.Length; i++)
			{
				BuildingModifierInfo buildingModifierInfo = m_Modifiers[i];
				buffer.Add(new BuildingModifierData(buildingModifierInfo.m_Type, buildingModifierInfo.m_Mode, buildingModifierInfo.m_Range));
			}
		}
	}
```


