# Game.Prefabs.UIGroupPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public abstract class UIGroupPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    protected UIGroupPrefab();

    public System.Void AddElement(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `protected UIGroupPrefab()`  

```csharp
protected UIGroupPrefab();
```


## Methods

- `public AddElement(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public void AddElement(EntityManager entityManager, Entity entity)
	{
		Entity entity2 = entityManager.World.GetExistingSystemManaged<PrefabSystem>().GetEntity(this);
		entityManager.GetBuffer<UIGroupElement>(entity2).Add(new UIGroupElement(entity));
		entityManager.GetBuffer<UnlockRequirement>(entity2).Add(new UnlockRequirement(entity, UnlockFlags.RequireAny));
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<UIGroupElement>());
		components.Add(ComponentType.ReadWrite<UnlockRequirement>());
		components.Add(ComponentType.ReadWrite<Locked>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		entityManager.GetBuffer<UnlockRequirement>(entity).Add(new UnlockRequirement(entity, UnlockFlags.RequireAny));
		base.LateInitialize(entityManager, entity);
	}
```


