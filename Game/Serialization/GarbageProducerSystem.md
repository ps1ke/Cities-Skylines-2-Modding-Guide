# Game.Serialization.GarbageProducerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageProducerSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.GarbageProducerSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_31347557_0;

    public GarbageProducerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.GarbageProducerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.GarbageProducerSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_31347557_0`  

```csharp
private Unity.Entities.EntityQuery __query_31347557_0;
```


## Constructors

- `public GarbageProducerSystem()`  

```csharp
[Preserve]
	public GarbageProducerSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<GarbageParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_31347557_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
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
		if (!(context.version < Version.garbageProducerFlags))
		{
			return;
		}
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<GarbageProducer>());
		GarbageParameterData singleton = __query_31347557_0.GetSingleton<GarbageParameterData>();
		NativeArray<Entity> nativeArray = entityQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (!base.EntityManager.TryGetBuffer(nativeArray[i], isReadOnly: true, out DynamicBuffer<IconElement> buffer))
			{
				continue;
			}
			for (int j = 0; j < buffer.Length; j++)
			{
				if (base.EntityManager.TryGetComponent<PrefabRef>(buffer[j].m_Icon, out var component) && component.m_Prefab == singleton.m_GarbageNotificationPrefab)
				{
					if (base.EntityManager.TryGetComponent<GarbageProducer>(nativeArray[i], out var component2) && (component2.m_Flags & GarbageProducerFlags.GarbagePilingUpWarning) == 0)
					{
						component2.m_Flags |= GarbageProducerFlags.GarbagePilingUpWarning;
						base.EntityManager.SetComponentData(nativeArray[i], component2);
					}
					break;
				}
			}
		}
		nativeArray.Dispose();
	}
```


## Nested types

- `Game.Serialization.GarbageProducerSystem+TypeHandle`  

