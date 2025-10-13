# Game.Serialization.HotspotFrameSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HotspotFrameSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.HotspotFrameSystem+TypeHandle __TypeHandle;

    public HotspotFrameSystem();

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

- `private Game.Serialization.HotspotFrameSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.HotspotFrameSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HotspotFrameSystem()`  

```csharp
[Preserve]
	public HotspotFrameSystem()
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
		m_Query = GetEntityQuery(ComponentType.ReadWrite<HotspotFrame>(), ComponentType.ReadWrite<InterpolatedTransform>(), ComponentType.ReadOnly<WeatherPhenomenon>());
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
		HotspotFrameJob jobData = new HotspotFrameJob
		{
			m_WeatherPhenomenonType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_WeatherPhenomenon_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HotspotFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Events_HotspotFrame_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_Query, base.Dependency);
	}
```


## Nested types

- `Game.Serialization.HotspotFrameSystem+HotspotFrameJob`  
- `Game.Serialization.HotspotFrameSystem+TypeHandle`  

