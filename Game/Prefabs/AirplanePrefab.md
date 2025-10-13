# Game.Prefabs.AirplanePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.AircraftPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AirplanePrefab : Game.Prefabs.AircraftPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Unity.Mathematics.float2 m_FlyingSpeed;
    public System.Single m_FlyingAcceleration;
    public System.Single m_FlyingBraking;
    public System.Single m_FlyingTurning;
    public System.Single m_FlyingAngularAcceleration;
    public System.Single m_ClimbAngle;
    public System.Single m_SlowPitchAngle;
    public System.Single m_TurningRollFactor;

    public AirplanePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float2 m_FlyingSpeed`  

```csharp
public Unity.Mathematics.float2 m_FlyingSpeed;
```

- `public System.Single m_FlyingAcceleration`  

```csharp
public System.Single m_FlyingAcceleration;
```

- `public System.Single m_FlyingBraking`  

```csharp
public System.Single m_FlyingBraking;
```

- `public System.Single m_FlyingTurning`  

```csharp
public System.Single m_FlyingTurning;
```

- `public System.Single m_FlyingAngularAcceleration`  

```csharp
public System.Single m_FlyingAngularAcceleration;
```

- `public System.Single m_ClimbAngle`  

```csharp
public System.Single m_ClimbAngle;
```

- `public System.Single m_SlowPitchAngle`  

```csharp
public System.Single m_SlowPitchAngle;
```

- `public System.Single m_TurningRollFactor`  

```csharp
public System.Single m_TurningRollFactor;
```


## Constructors

- `public AirplanePrefab()`  

```csharp
public AirplanePrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Airplane>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<AirplaneData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new AirplaneData
		{
			m_FlyingSpeed = m_FlyingSpeed / 3.6f,
			m_FlyingAcceleration = m_FlyingAcceleration,
			m_FlyingBraking = m_FlyingBraking,
			m_FlyingTurning = math.radians(m_FlyingTurning),
			m_FlyingAngularAcceleration = math.radians(m_FlyingAngularAcceleration),
			m_ClimbAngle = math.radians(m_ClimbAngle),
			m_SlowPitchAngle = math.radians(m_SlowPitchAngle),
			m_TurningRollFactor = m_TurningRollFactor
		});
	}
```


