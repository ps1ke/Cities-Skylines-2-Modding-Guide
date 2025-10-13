# Game.Prefabs.Effects.RandomTransform

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RandomTransform : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float3 m_MinAngle;
    public Unity.Mathematics.float3 m_MaxAngle;
    public Unity.Mathematics.float3 m_MinPosition;
    public Unity.Mathematics.float3 m_MaxPosition;

    public RandomTransform();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float3 m_MinAngle`  

```csharp
public Unity.Mathematics.float3 m_MinAngle;
```

- `public Unity.Mathematics.float3 m_MaxAngle`  

```csharp
public Unity.Mathematics.float3 m_MaxAngle;
```

- `public Unity.Mathematics.float3 m_MinPosition`  

```csharp
public Unity.Mathematics.float3 m_MinPosition;
```

- `public Unity.Mathematics.float3 m_MaxPosition`  

```csharp
public Unity.Mathematics.float3 m_MaxPosition;
```


## Constructors

- `public RandomTransform()`  

```csharp
public RandomTransform();
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
		components.Add(ComponentType.ReadWrite<RandomTransformData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		RandomTransformData componentData = default(RandomTransformData);
		componentData.m_AngleRange.min = math.radians(m_MinAngle);
		componentData.m_AngleRange.max = math.radians(m_MaxAngle);
		componentData.m_PositionRange.min = m_MinPosition;
		componentData.m_PositionRange.max = m_MaxPosition;
		entityManager.SetComponentData(entity, componentData);
	}
```


