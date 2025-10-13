# Game.Prefabs.HelicopterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.AircraftPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ExcludeGeneratedModTag`, `ComponentMenu`  

## Code

```csharp
public class HelicopterPrefab : Game.Prefabs.AircraftPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_FlyingMaxSpeed;
    public System.Single m_FlyingAcceleration;
    public System.Single m_FlyingAngularAcceleration;
    public System.Single m_AccelerationSwayFactor;
    public System.Single m_VelocitySwayFactor;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public HelicopterPrefab();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    protected virtual Game.Vehicles.HelicopterType GetHelicopterType();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_FlyingMaxSpeed`  

```csharp
public System.Single m_FlyingMaxSpeed;
```

- `public System.Single m_FlyingAcceleration`  

```csharp
public System.Single m_FlyingAcceleration;
```

- `public System.Single m_FlyingAngularAcceleration`  

```csharp
public System.Single m_FlyingAngularAcceleration;
```

- `public System.Single m_AccelerationSwayFactor`  

```csharp
public System.Single m_AccelerationSwayFactor;
```

- `public System.Single m_VelocitySwayFactor`  

```csharp
public System.Single m_VelocitySwayFactor;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public HelicopterPrefab()`  

```csharp
public HelicopterPrefab();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Helicopter>());
	}
```

- `protected virtual GetHelicopterType() : Game.Vehicles.HelicopterType`  

```csharp
protected virtual HelicopterType GetHelicopterType()
	{
		return HelicopterType.Helicopter;
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<HelicopterData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		HelicopterData componentData = default(HelicopterData);
		componentData.m_HelicopterType = GetHelicopterType();
		componentData.m_FlyingMaxSpeed = m_FlyingMaxSpeed / 3.6f;
		componentData.m_FlyingAcceleration = m_FlyingAcceleration;
		componentData.m_FlyingAngularAcceleration = math.radians(m_FlyingAngularAcceleration);
		componentData.m_AccelerationSwayFactor = m_AccelerationSwayFactor;
		componentData.m_VelocitySwayFactor = m_VelocitySwayFactor / componentData.m_FlyingMaxSpeed;
		entityManager.SetComponentData(entity, componentData);
	}
```


## Nested types

- `Game.Prefabs.HelicopterPrefab+<get_modTags>d__10`  

