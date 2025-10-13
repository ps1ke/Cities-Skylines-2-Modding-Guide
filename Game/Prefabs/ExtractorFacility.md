# Game.Prefabs.ExtractorFacility

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ExtractorFacility : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Colossal.Mathematics.Bounds1 m_RotationRange;
    public Colossal.Mathematics.Bounds1 m_HeightOffset;
    public System.Boolean m_RouteNeeded;
    public System.Boolean m_NetNeeded;

    public ExtractorFacility();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_RotationRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_RotationRange;
```

- `public Colossal.Mathematics.Bounds1 m_HeightOffset`  

```csharp
public Colossal.Mathematics.Bounds1 m_HeightOffset;
```

- `public System.Boolean m_RouteNeeded`  

```csharp
public System.Boolean m_RouteNeeded;
```

- `public System.Boolean m_NetNeeded`  

```csharp
public System.Boolean m_NetNeeded;
```


## Constructors

- `public ExtractorFacility()`  

```csharp
public ExtractorFacility();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.ExtractorFacility>());
		components.Add(ComponentType.ReadWrite<PointOfInterest>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ExtractorFacilityData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		ExtractorFacilityData componentData = default(ExtractorFacilityData);
		componentData.m_RotationRange.min = math.radians(m_RotationRange.min);
		componentData.m_RotationRange.max = math.radians(m_RotationRange.max);
		componentData.m_HeightOffset = m_HeightOffset;
		componentData.m_Requirements = ExtractorRequirementFlags.None;
		if (m_RouteNeeded)
		{
			componentData.m_Requirements |= ExtractorRequirementFlags.RouteConnect;
		}
		if (m_NetNeeded)
		{
			componentData.m_Requirements |= ExtractorRequirementFlags.NetConnect;
		}
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, new UpdateFrameData(14));
	}
```


