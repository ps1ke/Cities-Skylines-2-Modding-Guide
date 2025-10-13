# Game.Prefabs.HouseholdPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ArchetypePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HouseholdPrefab : Game.Prefabs.ArchetypePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_ResourceConsumption;
    public System.Int32 m_InitialWealthRange;
    public System.Int32 m_InitialWealthOffset;
    public System.Int32 m_InitialCarProbability;
    public System.Int32 m_ChildCount;
    public System.Int32 m_AdultCount;
    public System.Int32 m_ElderlyCount;
    public System.Int32 m_StudentCount;
    public System.Int32 m_FirstPetProbability;
    public System.Int32 m_NextPetProbability;
    public System.Boolean m_DynamicHousehold;
    public System.Int32 m_Weight;

    public HouseholdPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_ResourceConsumption`  

```csharp
public System.Int32 m_ResourceConsumption;
```

- `public System.Int32 m_InitialWealthRange`  

```csharp
public System.Int32 m_InitialWealthRange;
```

- `public System.Int32 m_InitialWealthOffset`  

```csharp
public System.Int32 m_InitialWealthOffset;
```

- `public System.Int32 m_InitialCarProbability`  

```csharp
public System.Int32 m_InitialCarProbability;
```

- `public System.Int32 m_ChildCount`  

```csharp
public System.Int32 m_ChildCount;
```

- `public System.Int32 m_AdultCount`  

```csharp
public System.Int32 m_AdultCount;
```

- `public System.Int32 m_ElderlyCount`  

```csharp
public System.Int32 m_ElderlyCount;
```

- `public System.Int32 m_StudentCount`  

```csharp
public System.Int32 m_StudentCount;
```

- `public System.Int32 m_FirstPetProbability`  

```csharp
public System.Int32 m_FirstPetProbability;
```

- `public System.Int32 m_NextPetProbability`  

```csharp
public System.Int32 m_NextPetProbability;
```

- `public System.Boolean m_DynamicHousehold`  

```csharp
public System.Boolean m_DynamicHousehold;
```

- `public System.Int32 m_Weight`  

```csharp
public System.Int32 m_Weight;
```


## Constructors

- `public HouseholdPrefab()`  

```csharp
public HouseholdPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Household>());
		components.Add(ComponentType.ReadWrite<HouseholdNeed>());
		components.Add(ComponentType.ReadWrite<HouseholdCitizen>());
		components.Add(ComponentType.ReadWrite<TaxPayer>());
		components.Add(ComponentType.ReadWrite<Game.Economy.Resources>());
		components.Add(ComponentType.ReadWrite<PropertySeeker>());
		components.Add(ComponentType.ReadWrite<UpdateFrame>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<HouseholdData>());
		if (m_DynamicHousehold)
		{
			components.Add(ComponentType.ReadWrite<DynamicHousehold>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new HouseholdData
		{
			m_InitialCarProbability = m_InitialCarProbability,
			m_InitialWealthOffset = m_InitialWealthOffset,
			m_InitialWealthRange = m_InitialWealthRange,
			m_ChildCount = m_ChildCount,
			m_AdultCount = m_AdultCount,
			m_ElderCount = m_ElderlyCount,
			m_StudentCount = m_StudentCount,
			m_FirstPetProbability = m_FirstPetProbability,
			m_NextPetProbability = m_NextPetProbability,
			m_Weight = m_Weight
		});
	}
```


