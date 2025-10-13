# Game.Prefabs.PolicySliderPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PolicyPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PolicySliderPrefab : Game.Prefabs.PolicyPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Colossal.Mathematics.Bounds1 m_SliderRange;
    public System.Single m_SliderDefault;
    public System.Single m_SliderStep;
    public Game.Prefabs.PolicySliderUnit m_Unit;

    public PolicySliderPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_SliderRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_SliderRange;
```

- `public System.Single m_SliderDefault`  

```csharp
public System.Single m_SliderDefault;
```

- `public System.Single m_SliderStep`  

```csharp
public System.Single m_SliderStep;
```

- `public Game.Prefabs.PolicySliderUnit m_Unit`  

```csharp
public Game.Prefabs.PolicySliderUnit m_Unit;
```


## Constructors

- `public PolicySliderPrefab()`  

```csharp
public PolicySliderPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<PolicySliderData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		PolicySliderData componentData = default(PolicySliderData);
		componentData.m_Range = m_SliderRange;
		componentData.m_Default = m_SliderDefault;
		componentData.m_Step = m_SliderStep;
		componentData.m_Unit = (int)m_Unit;
		entityManager.SetComponentData(entity, componentData);
	}
```


