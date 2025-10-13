# Game.Prefabs.VehicleSideEffects

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class VehicleSideEffects : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float2 m_RoadWear;
    public Unity.Mathematics.float2 m_NoisePollution;
    public Unity.Mathematics.float2 m_AirPollution;

    public VehicleSideEffects();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float2 m_RoadWear`  

```csharp
public Unity.Mathematics.float2 m_RoadWear;
```

- `public Unity.Mathematics.float2 m_NoisePollution`  

```csharp
public Unity.Mathematics.float2 m_NoisePollution;
```

- `public Unity.Mathematics.float2 m_AirPollution`  

```csharp
public Unity.Mathematics.float2 m_AirPollution;
```


## Constructors

- `public VehicleSideEffects()`  

```csharp
public VehicleSideEffects();
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
		components.Add(ComponentType.ReadWrite<VehicleSideEffectData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		VehicleSideEffectData componentData = default(VehicleSideEffectData);
		componentData.m_Min = new float3(m_RoadWear.x, m_NoisePollution.x, m_AirPollution.x);
		componentData.m_Max = new float3(m_RoadWear.y, m_NoisePollution.y, m_AirPollution.y);
		entityManager.SetComponentData(entity, componentData);
	}
```


