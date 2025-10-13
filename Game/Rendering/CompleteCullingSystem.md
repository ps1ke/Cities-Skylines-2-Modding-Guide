# Game.Rendering.CompleteCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompleteCullingSystem : Game.GameSystemBase
{
    private Game.Rendering.PreCullingSystem m_CullingSystem;
    private Game.Rendering.CompleteCullingSystem+TypeHandle __TypeHandle;

    public CompleteCullingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.PreCullingSystem m_CullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_CullingSystem;
```

- `private Game.Rendering.CompleteCullingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.CompleteCullingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompleteCullingSystem()`  

```csharp
[Preserve]
	public CompleteCullingSystem()
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
		m_CullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
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
		JobHandle dependencies;
		JobHandle jobHandle = IJobExtensions.Schedule(new CullingCleanupJob
		{
			m_CullingInfo = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CullingData = m_CullingSystem.GetCullingData(readOnly: false, out dependencies)
		}, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_CullingSystem.AddCullingDataWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Rendering.CompleteCullingSystem+CullingCleanupJob`  
- `Game.Rendering.CompleteCullingSystem+TypeHandle`  

