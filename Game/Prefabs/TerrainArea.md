# Game.Prefabs.TerrainArea

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TerrainArea : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_HeightOffset;
    public System.Single m_SlopeWidth;
    public System.Single m_NoiseScale;
    public System.Single m_NoiseFactor;
    public System.Boolean m_AbsoluteHeight;

    public TerrainArea();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_HeightOffset`  

```csharp
public System.Single m_HeightOffset;
```

- `public System.Single m_SlopeWidth`  

```csharp
public System.Single m_SlopeWidth;
```

- `public System.Single m_NoiseScale`  

```csharp
public System.Single m_NoiseScale;
```

- `public System.Single m_NoiseFactor`  

```csharp
public System.Single m_NoiseFactor;
```

- `public System.Boolean m_AbsoluteHeight`  

```csharp
public System.Boolean m_AbsoluteHeight;
```


## Constructors

- `public TerrainArea()`  

```csharp
public TerrainArea();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Terrain>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<TerrainAreaData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		TerrainAreaData componentData = default(TerrainAreaData);
		componentData.m_HeightOffset = m_HeightOffset;
		componentData.m_SlopeWidth = m_SlopeWidth;
		componentData.m_NoiseScale = 1f / math.max(0.001f, m_NoiseScale);
		componentData.m_NoiseFactor = m_NoiseFactor;
		componentData.m_AbsoluteHeight = (m_AbsoluteHeight ? 1f : 0f);
		entityManager.SetComponentData(entity, componentData);
	}
```


