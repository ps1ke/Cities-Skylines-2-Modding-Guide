# Game.Common.NativeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class NativeSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_EntityQuery;
    private Unity.Entities.EntityQuery m_NativeQuery;

    public NativeSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_EntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_EntityQuery;
```

- `private Unity.Entities.EntityQuery m_NativeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NativeQuery;
```


## Constructors

- `public NativeSystem()`  

```csharp
[Preserve]
	public NativeSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_EntityQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Game.Net.Node>(),
				ComponentType.ReadOnly<Object>(),
				ComponentType.ReadOnly<Area>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Native>() }
		});
		m_NativeQuery = GetEntityQuery(ComponentType.ReadOnly<Native>());
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		switch (m_LoadGameSystem.context.purpose)
		{
		case Purpose.NewGame:
			base.EntityManager.AddComponent<Native>(m_EntityQuery);
			break;
		case Purpose.LoadMap:
			base.EntityManager.RemoveComponent<Native>(m_NativeQuery);
			break;
		}
	}
```


