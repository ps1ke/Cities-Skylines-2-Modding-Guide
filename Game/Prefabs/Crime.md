# Game.Prefabs.Crime

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Crime : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EventTargetType m_RandomTargetType;
    public Game.Prefabs.CrimeType m_CrimeType;
    public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
    public Colossal.Mathematics.Bounds1 m_RecurrenceProbability;
    public Colossal.Mathematics.Bounds1 m_AlarmDelay;
    public Colossal.Mathematics.Bounds1 m_CrimeDuration;
    public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute;
    public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative;
    public Colossal.Mathematics.Bounds1 m_JailTimeRange;
    public Colossal.Mathematics.Bounds1 m_PrisonTimeRange;
    public System.Single m_PrisonProbability;

    public Crime();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomTargetType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomTargetType;
```

- `public Game.Prefabs.CrimeType m_CrimeType`  

```csharp
public Game.Prefabs.CrimeType m_CrimeType;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_RecurrenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_RecurrenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_AlarmDelay`  

```csharp
public Colossal.Mathematics.Bounds1 m_AlarmDelay;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeDuration`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeDuration;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative;
```

- `public Colossal.Mathematics.Bounds1 m_JailTimeRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_JailTimeRange;
```

- `public Colossal.Mathematics.Bounds1 m_PrisonTimeRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_PrisonTimeRange;
```

- `public System.Single m_PrisonProbability`  

```csharp
public System.Single m_PrisonProbability;
```


## Constructors

- `public Crime()`  

```csharp
public Crime();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Events.Crime>());
		components.Add(ComponentType.ReadWrite<TargetElement>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<CrimeData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		CrimeData componentData = default(CrimeData);
		componentData.m_RandomTargetType = m_RandomTargetType;
		componentData.m_CrimeType = m_CrimeType;
		componentData.m_OccurenceProbability = m_OccurenceProbability;
		componentData.m_RecurrenceProbability = m_RecurrenceProbability;
		componentData.m_AlarmDelay = m_AlarmDelay;
		componentData.m_CrimeDuration = m_CrimeDuration;
		componentData.m_CrimeIncomeAbsolute = m_CrimeIncomeAbsolute;
		componentData.m_CrimeIncomeRelative = m_CrimeIncomeRelative;
		componentData.m_JailTimeRange = m_JailTimeRange;
		componentData.m_PrisonTimeRange = m_PrisonTimeRange;
		componentData.m_PrisonProbability = m_PrisonProbability;
		entityManager.SetComponentData(entity, componentData);
	}
```


