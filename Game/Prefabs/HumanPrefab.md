# Game.Prefabs.HumanPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.CreaturePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HumanPrefab : Game.Prefabs.CreaturePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_WalkSpeed;
    public System.Single m_RunSpeed;
    public System.Single m_Acceleration;

    public HumanPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_WalkSpeed`  

```csharp
public System.Single m_WalkSpeed;
```

- `public System.Single m_RunSpeed`  

```csharp
public System.Single m_RunSpeed;
```

- `public System.Single m_Acceleration`  

```csharp
public System.Single m_Acceleration;
```


## Constructors

- `public HumanPrefab()`  

```csharp
public HumanPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Human>());
		components.Add(ComponentType.ReadWrite<HumanNavigation>());
		components.Add(ComponentType.ReadWrite<Queue>());
		components.Add(ComponentType.ReadWrite<PathOwner>());
		components.Add(ComponentType.ReadWrite<PathElement>());
		components.Add(ComponentType.ReadWrite<Target>());
		components.Add(ComponentType.ReadWrite<Blocker>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<HumanData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new HumanData
		{
			m_WalkSpeed = m_WalkSpeed / 3.6f,
			m_RunSpeed = m_RunSpeed / 3.6f,
			m_Acceleration = m_Acceleration
		});
	}
```


