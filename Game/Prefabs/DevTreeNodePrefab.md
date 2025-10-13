# Game.Prefabs.DevTreeNodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `RequireComponent`  

## Code

```csharp
public class DevTreeNodePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ServicePrefab m_Service;
    public Game.Prefabs.DevTreeNodePrefab[] m_Requirements;
    public System.Int32 m_Cost;
    public System.Int32 m_HorizontalPosition;
    public System.Single m_VerticalPosition;
    public System.String m_IconPath;
    public Game.Prefabs.PrefabBase m_IconPrefab;

    public DevTreeNodePrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    private System.Boolean HasRequirements();
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ServicePrefab m_Service`  

```csharp
public Game.Prefabs.ServicePrefab m_Service;
```

- `public Game.Prefabs.DevTreeNodePrefab[] m_Requirements`  

```csharp
public Game.Prefabs.DevTreeNodePrefab[] m_Requirements;
```

- `public System.Int32 m_Cost`  

```csharp
public System.Int32 m_Cost;
```

- `public System.Int32 m_HorizontalPosition`  

```csharp
public System.Int32 m_HorizontalPosition;
```

- `public System.Single m_VerticalPosition`  

```csharp
public System.Single m_VerticalPosition;
```

- `public System.String m_IconPath`  

```csharp
public System.String m_IconPath;
```

- `public Game.Prefabs.PrefabBase m_IconPrefab`  

```csharp
public Game.Prefabs.PrefabBase m_IconPrefab;
```


## Constructors

- `public DevTreeNodePrefab()`  

```csharp
public DevTreeNodePrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Service != null)
		{
			prefabs.Add(m_Service);
		}
		if (m_Requirements == null)
		{
			return;
		}
		DevTreeNodePrefab[] requirements = m_Requirements;
		foreach (DevTreeNodePrefab devTreeNodePrefab in requirements)
		{
			if (devTreeNodePrefab != null)
			{
				prefabs.Add(devTreeNodePrefab);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<DevTreeNodeData>());
		if (HasRequirements())
		{
			components.Add(ComponentType.ReadWrite<DevTreeNodeRequirement>());
		}
		if (m_Cost == 0)
		{
			components.Add(ComponentType.ReadWrite<DevTreeNodeAutoUnlock>());
		}
	}
```

- `private HasRequirements() : System.Boolean`  

```csharp
private bool HasRequirements()
	{
		if (m_Requirements != null)
		{
			DevTreeNodePrefab[] requirements = m_Requirements;
			for (int i = 0; i < requirements.Length; i++)
			{
				if (requirements[i] != null)
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		Entity entity2 = existingSystemManaged.GetEntity(m_Service);
		entityManager.SetComponentData(entity, new DevTreeNodeData
		{
			m_Cost = m_Cost,
			m_Service = entity2
		});
		if (!entityManager.HasComponent<DevTreeNodeRequirement>(entity))
		{
			return;
		}
		DynamicBuffer<DevTreeNodeRequirement> buffer = entityManager.GetBuffer<DevTreeNodeRequirement>(entity);
		DevTreeNodePrefab[] requirements = m_Requirements;
		foreach (DevTreeNodePrefab devTreeNodePrefab in requirements)
		{
			if (devTreeNodePrefab != null)
			{
				Entity entity3 = existingSystemManaged.GetEntity(devTreeNodePrefab);
				buffer.Add(new DevTreeNodeRequirement
				{
					m_Node = entity3
				});
			}
		}
	}
```


