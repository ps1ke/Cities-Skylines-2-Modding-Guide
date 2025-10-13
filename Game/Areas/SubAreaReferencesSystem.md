# Game.Areas.SubAreaReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubAreaReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_SubAreaQuery;
    private Game.Areas.SubAreaReferencesSystem+TypeHandle __TypeHandle;

    public SubAreaReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SubAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubAreaQuery;
```

- `private Game.Areas.SubAreaReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.SubAreaReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubAreaReferencesSystem()`  

```csharp
[Preserve]
	public SubAreaReferencesSystem()
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
		m_SubAreaQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Area>(),
				ComponentType.ReadOnly<Owner>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		RequireForUpdate(m_SubAreaQuery);
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
		UpdateSubAreaReferencesJob jobData = new UpdateSubAreaReferencesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RW_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_SubAreaQuery, base.Dependency);
	}
```


## Nested types

- `Game.Areas.SubAreaReferencesSystem+UpdateSubAreaReferencesJob`  
- `Game.Areas.SubAreaReferencesSystem+TypeHandle`  

