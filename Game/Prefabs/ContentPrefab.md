# Game.Prefabs.ContentPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ContentPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public ContentPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public System.Boolean IsAvailable();
}
```


## Constructors

- `public ContentPrefab()`  

```csharp
public ContentPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ContentData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		ContentData componentData = entityManager.GetComponentData<ContentData>(entity);
		if (TryGet<DlcRequirement>(out var component))
		{
			componentData.m_Flags |= ContentFlags.RequireDlc;
			componentData.m_DlcID = component.m_Dlc.id;
		}
		if (Has<PdxLoginRequirement>())
		{
			componentData.m_Flags |= ContentFlags.RequirePdxLogin;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```

- `public IsAvailable() : System.Boolean`  

```csharp
public bool IsAvailable()
	{
		foreach (ComponentBase component in components)
		{
			if (component is ContentRequirementBase contentRequirementBase && !contentRequirementBase.CheckRequirement())
			{
				return false;
			}
		}
		return true;
	}
```


