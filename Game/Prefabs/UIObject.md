# Game.Prefabs.UIObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.UIGroupPrefab m_Group;
    public System.Int32 m_Priority;
    public System.String m_Icon;
    public System.Boolean m_IsDebugObject;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public UIObject();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.UIGroupPrefab m_Group`  

```csharp
public Game.Prefabs.UIGroupPrefab m_Group;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.String m_Icon`  

```csharp
public System.String m_Icon;
```

- `public System.Boolean m_IsDebugObject`  

```csharp
public System.Boolean m_IsDebugObject;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public UIObject()`  

```csharp
public UIObject();
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
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Group != null)
		{
			prefabs.Add(m_Group);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		if (!m_IsDebugObject || UnityEngine.Debug.isDebugBuild)
		{
			components.Add(ComponentType.ReadWrite<UIObjectData>());
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (!m_IsDebugObject || UnityEngine.Debug.isDebugBuild)
		{
			Entity entity2 = Entity.Null;
			if (m_Group != null)
			{
				entity2 = entityManager.World.GetExistingSystemManaged<PrefabSystem>().GetEntity(m_Group);
				m_Group.AddElement(entityManager, entity);
			}
			entityManager.SetComponentData(entity, new UIObjectData
			{
				m_Group = entity2,
				m_Priority = m_Priority
			});
		}
	}
```


## Nested types

- `Game.Prefabs.UIObject+<get_modTags>d__9`  

