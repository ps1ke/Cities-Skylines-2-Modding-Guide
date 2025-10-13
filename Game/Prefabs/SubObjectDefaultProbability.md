# Game.Prefabs.SubObjectDefaultProbability

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SubObjectDefaultProbability : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_DefaultProbability;
    public Game.Objects.RotationSymmetry m_RotationSymmetry;

    public SubObjectDefaultProbability();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_DefaultProbability`  

```csharp
public System.Int32 m_DefaultProbability;
```

- `public Game.Objects.RotationSymmetry m_RotationSymmetry`  

```csharp
public Game.Objects.RotationSymmetry m_RotationSymmetry;
```


## Constructors

- `public SubObjectDefaultProbability()`  

```csharp
public SubObjectDefaultProbability();
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
		components.Add(ComponentType.ReadWrite<PlaceableObjectData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		if (base.prefab.Has<ServiceUpgrade>())
		{
			ComponentBase.baseLog.ErrorFormat(base.prefab, "ServiceUpgrade cannot have SubObjectDefaultProbability: {0}", base.prefab.name);
		}
		PlaceableObjectData componentData = entityManager.GetComponentData<PlaceableObjectData>(entity);
		componentData.m_DefaultProbability = (byte)m_DefaultProbability;
		componentData.m_RotationSymmetry = m_RotationSymmetry;
		componentData.m_Flags |= PlacementFlags.HasProbability;
		entityManager.SetComponentData(entity, componentData);
	}
```


