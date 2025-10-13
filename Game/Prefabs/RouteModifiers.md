# Game.Prefabs.RouteModifiers

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RouteModifiers : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.RouteModifierInfo[] m_Modifiers;

    public RouteModifiers();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.RouteModifierInfo[] m_Modifiers`  

```csharp
public Game.Prefabs.RouteModifierInfo[] m_Modifiers;
```


## Constructors

- `public RouteModifiers()`  

```csharp
public RouteModifiers();
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
		components.Add(ComponentType.ReadWrite<RouteModifierData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		if (m_Modifiers != null)
		{
			DynamicBuffer<RouteModifierData> buffer = entityManager.GetBuffer<RouteModifierData>(entity);
			for (int i = 0; i < m_Modifiers.Length; i++)
			{
				RouteModifierInfo routeModifierInfo = m_Modifiers[i];
				buffer.Add(new RouteModifierData(routeModifierInfo.m_Type, routeModifierInfo.m_Mode, routeModifierInfo.m_Range));
			}
		}
	}
```


