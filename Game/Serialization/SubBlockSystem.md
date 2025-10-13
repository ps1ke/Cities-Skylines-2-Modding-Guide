# Game.Serialization.SubBlockSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubBlockSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.SubBlockSystem+TypeHandle __TypeHandle;

    public SubBlockSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.SubBlockSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.SubBlockSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubBlockSystem()`  

```csharp
[Preserve]
	public SubBlockSystem()
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
		m_Query = GetEntityQuery(ComponentType.ReadOnly<Block>(), ComponentType.ReadOnly<Owner>());
		RequireForUpdate(m_Query);
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
		SubBlockJob jobData = new SubBlockJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubBlocks = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_SubBlock_RW_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_Query, base.Dependency);
	}
```


## Nested types

- `Game.Serialization.SubBlockSystem+SubBlockJob`  
- `Game.Serialization.SubBlockSystem+TypeHandle`  

