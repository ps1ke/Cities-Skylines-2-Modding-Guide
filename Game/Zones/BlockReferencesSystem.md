# Game.Zones.BlockReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BlockReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BlockQuery;
    private Game.Zones.BlockReferencesSystem+TypeHandle __TypeHandle;

    public BlockReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_BlockQuery;
```

- `private Game.Zones.BlockReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Zones.BlockReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BlockReferencesSystem()`  

```csharp
[Preserve]
	public BlockReferencesSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_BlockQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Block>(),
				ComponentType.ReadOnly<Owner>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		RequireForUpdate(m_BlockQuery);
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
		UpdateBlockReferencesJob jobData = new UpdateBlockReferencesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Blocks = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_SubBlock_RW_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_BlockQuery, base.Dependency);
	}
```


## Nested types

- `Game.Zones.BlockReferencesSystem+UpdateBlockReferencesJob`  
- `Game.Zones.BlockReferencesSystem+TypeHandle`  

