# Game.Tools.GenerateWaterSourcesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateWaterSourcesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityArchetype m_WaterSourceArchetype;
    private Game.Tools.GenerateWaterSourcesSystem+TypeHandle __TypeHandle;

    public GenerateWaterSourcesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityArchetype m_WaterSourceArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_WaterSourceArchetype;
```

- `private Game.Tools.GenerateWaterSourcesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateWaterSourcesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateWaterSourcesSystem()`  

```csharp
[Preserve]
	public GenerateWaterSourcesSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier1>();
		m_DefinitionQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<CreationDefinition>(),
				ComponentType.ReadOnly<Updated>()
			},
			Any = new ComponentType[1] { ComponentType.ReadOnly<WaterSourceDefinition>() }
		});
		m_WaterSourceArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<WaterSourceData>(), ComponentType.ReadWrite<Transform>(), ComponentType.ReadWrite<Temp>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		RequireForUpdate(m_DefinitionQuery);
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
		GenerateBrushesJob jobData = new GenerateBrushesJob
		{
			m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterSourceDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_WaterSourceDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterSourceArchetype = m_WaterSourceArchetype,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_DefinitionQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Tools.GenerateWaterSourcesSystem+GenerateBrushesJob`  
- `Game.Tools.GenerateWaterSourcesSystem+TypeHandle`  

