# Game.Prefabs.StandingObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class StandingObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float3 m_LegSize;
    public Unity.Mathematics.float2 m_LegGap;
    public System.Boolean m_CircularLeg;

    public StandingObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float3 m_LegSize`  

```csharp
public Unity.Mathematics.float3 m_LegSize;
```

- `public Unity.Mathematics.float2 m_LegGap`  

```csharp
public Unity.Mathematics.float2 m_LegGap;
```

- `public System.Boolean m_CircularLeg`  

```csharp
public System.Boolean m_CircularLeg;
```


## Constructors

- `public StandingObject()`  

```csharp
public StandingObject();
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
		components.Add(ComponentType.ReadWrite<ObjectGeometryData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		ObjectGeometryData componentData = entityManager.GetComponentData<ObjectGeometryData>(entity);
		componentData.m_LegSize = m_LegSize;
		componentData.m_LegOffset = math.select(default(float2), (m_LegGap + m_LegSize.xz) * 0.5f, m_LegGap != 0f);
		componentData.m_Flags |= (GeometryFlags)(m_CircularLeg ? 384 : 128);
		entityManager.SetComponentData(entity, componentData);
	}
```


