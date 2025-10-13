# Game.Serialization.DataMigration.ShortLaneRemoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class ShortLaneRemoveSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_Query;

    public ShortLaneRemoveSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```


## Constructors

- `public ShortLaneRemoveSystem()`  

```csharp
[Preserve]
	public ShortLaneRemoveSystem()
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
		m_Query = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<SubLane>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Node>()
			}
		});
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_LoadGameSystem.context.format.Has(FormatTags.ShortLaneOptimization) && !m_Query.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Updated>(m_Query);
		}
	}
```


