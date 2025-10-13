# Game.Rendering.EventInterpolateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventInterpolateSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Game.Rendering.EventInterpolateSystem+TypeHandle __TypeHandle;

    public EventInterpolateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Game.Rendering.EventInterpolateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.EventInterpolateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EventInterpolateSystem()`  

```csharp
[Preserve]
	public EventInterpolateSystem()
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
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<WeatherPhenomenon>(), ComponentType.ReadOnly<HotspotFrame>(), ComponentType.ReadWrite<InterpolatedTransform>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_EventQuery);
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
		UpdateTransformDataJob jobData = new UpdateTransformDataJob
		{
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_HotspotFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Events_HotspotFrame_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_EventQuery, base.Dependency);
	}
```


## Nested types

- `Game.Rendering.EventInterpolateSystem+UpdateTransformDataJob`  
- `Game.Rendering.EventInterpolateSystem+TypeHandle`  

