# Game.Prefabs.MatchPieceVertices

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MatchPieceVertices : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single[] m_Offsets;

    public MatchPieceVertices();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single[] m_Offsets`  

```csharp
public System.Single[] m_Offsets;
```


## Constructors

- `public MatchPieceVertices()`  

```csharp
public MatchPieceVertices();
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
		components.Add(ComponentType.ReadWrite<NetVertexMatchData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		NetVertexMatchData componentData = new NetVertexMatchData
		{
			m_Offsets = float.NaN
		};
		if (m_Offsets != null)
		{
			if (m_Offsets.Length >= 1)
			{
				componentData.m_Offsets.x = m_Offsets[0];
			}
			if (m_Offsets.Length >= 2)
			{
				componentData.m_Offsets.y = m_Offsets[1];
			}
			if (m_Offsets.Length >= 3)
			{
				componentData.m_Offsets.z = m_Offsets[2];
			}
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


