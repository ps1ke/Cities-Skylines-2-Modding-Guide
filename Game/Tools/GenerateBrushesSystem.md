# Game.Tools.GenerateBrushesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateBrushesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Game.Tools.GenerateBrushesSystem+TypeHandle __TypeHandle;

    public GenerateBrushesSystem();

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

- `private Game.Tools.GenerateBrushesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateBrushesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateBrushesSystem()`  

```csharp
[Preserve]
	public GenerateBrushesSystem()
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
			Any = new ComponentType[1] { ComponentType.ReadOnly<BrushDefinition>() }
		});
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
			m_BrushDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_BrushDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBrushData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BrushData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTerraformingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TerraformingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_DefinitionQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Tools.GenerateBrushesSystem+GenerateBrushesJob`  
- `Game.Tools.GenerateBrushesSystem+TypeHandle`  

