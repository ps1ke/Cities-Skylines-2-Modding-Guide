# Game.Prefabs.ToolError

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ToolError : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Tools.ErrorType m_Error;
    public System.Boolean m_TemporaryOnly;
    public System.Boolean m_DisableInGame;
    public System.Boolean m_DisableInEditor;

    public ToolError();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Tools.ErrorType m_Error`  

```csharp
public Game.Tools.ErrorType m_Error;
```

- `public System.Boolean m_TemporaryOnly`  

```csharp
public System.Boolean m_TemporaryOnly;
```

- `public System.Boolean m_DisableInGame`  

```csharp
public System.Boolean m_DisableInGame;
```

- `public System.Boolean m_DisableInEditor`  

```csharp
public System.Boolean m_DisableInEditor;
```


## Constructors

- `public ToolError()`  

```csharp
public ToolError();
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
		components.Add(ComponentType.ReadWrite<ToolErrorData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		ToolErrorData componentData = default(ToolErrorData);
		componentData.m_Error = m_Error;
		componentData.m_Flags = (ToolErrorFlags)0;
		if (m_TemporaryOnly)
		{
			componentData.m_Flags |= ToolErrorFlags.TemporaryOnly;
		}
		if (m_DisableInGame)
		{
			componentData.m_Flags |= ToolErrorFlags.DisableInGame;
		}
		if (m_DisableInEditor)
		{
			componentData.m_Flags |= ToolErrorFlags.DisableInEditor;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


