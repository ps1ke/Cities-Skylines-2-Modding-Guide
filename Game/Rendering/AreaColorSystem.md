# Game.Rendering.AreaColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaColorSystem : Game.GameSystemBase
{
    private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Game.Rendering.AreaColorSystem+TypeHandle __TypeHandle;

    public AreaColorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.AreaBatchSystem m_AreaBatchSystem`  

```csharp
private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Game.Rendering.AreaColorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AreaColorSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaColorSystem()`  

```csharp
[Preserve]
	public AreaColorSystem()
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
		m_AreaBatchSystem = base.World.GetOrCreateSystemManaged<AreaBatchSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_AreaQuery = GetEntityQuery(ComponentType.ReadOnly<Batch>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
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
		if (m_ToolSystem.activeInfoview != null)
		{
			JobHandle dependencies;
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new FillColorDataJob
			{
				m_BatchType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Batch_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Color_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AreaColorData = m_AreaBatchSystem.GetColorData(out dependencies)
			}, m_AreaQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
			m_AreaBatchSystem.AddColorWriter(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Rendering.AreaColorSystem+FillColorDataJob`  
- `Game.Rendering.AreaColorSystem+TypeHandle`  

