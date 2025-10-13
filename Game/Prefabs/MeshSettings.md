# Game.Prefabs.MeshSettings

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MeshSettings : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.RenderPrefab m_MissingObjectMesh;
    public Game.Prefabs.RenderPrefab m_DefaultBaseMesh;
    public Game.Prefabs.NetSectionPrefab m_MissingNetSection;

    public MeshSettings();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.RenderPrefab m_MissingObjectMesh`  

```csharp
public Game.Prefabs.RenderPrefab m_MissingObjectMesh;
```

- `public Game.Prefabs.RenderPrefab m_DefaultBaseMesh`  

```csharp
public Game.Prefabs.RenderPrefab m_DefaultBaseMesh;
```

- `public Game.Prefabs.NetSectionPrefab m_MissingNetSection`  

```csharp
public Game.Prefabs.NetSectionPrefab m_MissingNetSection;
```


## Constructors

- `public MeshSettings()`  

```csharp
public MeshSettings();
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
		prefabs.Add(m_MissingObjectMesh);
		prefabs.Add(m_DefaultBaseMesh);
		prefabs.Add(m_MissingNetSection);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<MeshSettingsData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		MeshSettingsData componentData = new MeshSettingsData
		{
			m_MissingObjectMesh = existingSystemManaged.GetEntity(m_MissingObjectMesh),
			m_DefaultBaseMesh = existingSystemManaged.GetEntity(m_DefaultBaseMesh),
			m_MissingNetSection = existingSystemManaged.GetEntity(m_MissingNetSection)
		};
		entityManager.SetComponentData(entity, componentData);
	}
```


