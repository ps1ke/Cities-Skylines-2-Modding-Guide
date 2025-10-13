# Game.Prefabs.EducationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EducationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase m_EducationServicePrefab;
    public System.Single m_InoperableSchoolLeaveProbability;
    public System.Single m_EnterHighSchoolProbability;
    public System.Single m_AdultEnterHighSchoolProbability;
    public System.Single m_WorkerContinueEducationProbability;

    public EducationPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_EducationServicePrefab`  

```csharp
public Game.Prefabs.PrefabBase m_EducationServicePrefab;
```

- `public System.Single m_InoperableSchoolLeaveProbability`  

```csharp
public System.Single m_InoperableSchoolLeaveProbability;
```

- `public System.Single m_EnterHighSchoolProbability`  

```csharp
public System.Single m_EnterHighSchoolProbability;
```

- `public System.Single m_AdultEnterHighSchoolProbability`  

```csharp
public System.Single m_AdultEnterHighSchoolProbability;
```

- `public System.Single m_WorkerContinueEducationProbability`  

```csharp
public System.Single m_WorkerContinueEducationProbability;
```


## Constructors

- `public EducationPrefab()`  

```csharp
public EducationPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<EducationParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new EducationParameterData
		{
			m_EducationServicePrefab = orCreateSystemManaged.GetEntity(m_EducationServicePrefab),
			m_InoperableSchoolLeaveProbability = m_InoperableSchoolLeaveProbability,
			m_EnterHighSchoolProbability = m_EnterHighSchoolProbability,
			m_AdultEnterHighSchoolProbability = m_AdultEnterHighSchoolProbability,
			m_WorkerContinueEducationProbability = m_WorkerContinueEducationProbability
		});
	}
```


