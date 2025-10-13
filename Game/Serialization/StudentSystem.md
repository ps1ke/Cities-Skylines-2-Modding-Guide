# Game.Serialization.StudentSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StudentSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_StudentQuery;
    private Game.Serialization.StudentSystem+TypeHandle __TypeHandle;

    public StudentSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_StudentQuery`  

```csharp
private Unity.Entities.EntityQuery m_StudentQuery;
```

- `private Game.Serialization.StudentSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.StudentSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public StudentSystem()`  

```csharp
[Preserve]
	public StudentSystem()
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
		m_StudentQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Citizens.Student>());
		RequireForUpdate(m_StudentQuery);
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
		StudentJob jobData = new StudentJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_StudentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Student_RW_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_StudentQuery, base.Dependency);
	}
```


## Nested types

- `Game.Serialization.StudentSystem+StudentJob`  
- `Game.Serialization.StudentSystem+TypeHandle`  

