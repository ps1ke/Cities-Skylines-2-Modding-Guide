# Game.Prefabs.PersonalCar

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PersonalCar : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_PassengerCapacity;
    public System.Int32 m_BaggageCapacity;
    public System.Int32 m_CostToDrive;
    public System.Int32 m_Probability;

    public PersonalCar();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_PassengerCapacity`  

```csharp
public System.Int32 m_PassengerCapacity;
```

- `public System.Int32 m_BaggageCapacity`  

```csharp
public System.Int32 m_BaggageCapacity;
```

- `public System.Int32 m_CostToDrive`  

```csharp
public System.Int32 m_CostToDrive;
```

- `public System.Int32 m_Probability`  

```csharp
public System.Int32 m_Probability;
```


## Constructors

- `public PersonalCar()`  

```csharp
public PersonalCar();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Vehicles.PersonalCar>());
		components.Add(ComponentType.ReadWrite<Passenger>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PersonalCarData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new PersonalCarData
		{
			m_PassengerCapacity = m_PassengerCapacity,
			m_BaggageCapacity = m_BaggageCapacity,
			m_CostToDrive = m_CostToDrive,
			m_Probability = m_Probability
		});
	}
```


