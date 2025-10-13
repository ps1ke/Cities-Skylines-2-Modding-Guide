# Game.Debug.AreaDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_AreaGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_LotOption;
    private Game.Debug.BaseDebugSystem+Option m_DistrictOption;
    private Game.Debug.BaseDebugSystem+Option m_MapTileOption;
    private Game.Debug.BaseDebugSystem+Option m_SpaceOption;
    private Game.Debug.BaseDebugSystem+Option m_SurfaceOption;
    private Game.Debug.AreaDebugSystem+TypeHandle __TypeHandle;

    public AreaDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AreaGroup`  

```csharp
private Unity.Entities.EntityQuery m_AreaGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_LotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LotOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_DistrictOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_DistrictOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MapTileOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MapTileOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_SpaceOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SpaceOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_SurfaceOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SurfaceOption;
```

- `private Game.Debug.AreaDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.AreaDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaDebugSystem()`  

```csharp
[Preserve]
	public AreaDebugSystem()
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
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_AreaGroup = GetEntityQuery(ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Node>(), ComponentType.ReadOnly<Triangle>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Hidden>());
		m_LotOption = AddOption("Lots", defaultEnabled: true);
		m_DistrictOption = AddOption("Districts", defaultEnabled: true);
		m_MapTileOption = AddOption("Map Tiles", defaultEnabled: false);
		m_SpaceOption = AddOption("Spaces", defaultEnabled: true);
		m_SurfaceOption = AddOption("Surfaces", defaultEnabled: true);
		RequireForUpdate(m_AreaGroup);
		base.Enabled = false;
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

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new AreaGizmoJob
		{
			m_LotOption = m_LotOption.enabled,
			m_DistrictOption = m_DistrictOption.enabled,
			m_MapTileOption = m_MapTileOption.enabled,
			m_SpaceOption = m_SpaceOption.enabled,
			m_SurfaceOption = m_SurfaceOption.enabled,
			m_AreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Area_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_District_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MapTileType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_MapTile_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpaceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Space_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SurfaceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Surface_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ErrorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Error_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, m_AreaGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.AreaDebugSystem+AreaGizmoJob`  
- `Game.Debug.AreaDebugSystem+TypeHandle`  

