# Game.Serialization.HouseholdSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

## Code

```csharp
public class HouseholdSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_MovingInHouseholdQuery;

    public HouseholdSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_MovingInHouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_MovingInHouseholdQuery;
```


## Constructors

- `public HouseholdSystem()`  

```csharp
[Preserve]
	public HouseholdSystem()
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
		m_MovingInHouseholdQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Household>() },
			None = new ComponentType[5]
			{
				ComponentType.ReadOnly<TouristHousehold>(),
				ComponentType.ReadOnly<CommuterHousehold>(),
				ComponentType.ReadOnly<MovingAway>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		RequireForUpdate(m_MovingInHouseholdQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (!(context.version < Version.clearMovingInHousehold))
		{
			return;
		}
		NativeArray<Entity> nativeArray = m_MovingInHouseholdQuery.ToEntityArray(Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (base.EntityManager.TryGetComponent<Household>(nativeArray[i], out var component) && (component.m_Flags & HouseholdFlags.MovedIn) == 0 && (!base.EntityManager.TryGetComponent<PropertyRenter>(nativeArray[i], out var component2) || component2.m_Property == Entity.Null))
			{
				base.EntityManager.AddComponent<Deleted>(nativeArray[i]);
			}
		}
		nativeArray.Dispose();
	}
```


