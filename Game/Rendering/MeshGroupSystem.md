# Game.Rendering.MeshGroupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeshGroupSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private System.Boolean m_Loaded;
    private Game.Rendering.MeshGroupSystem+TypeHandle __TypeHandle;

    public MeshGroupSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.MeshGroupSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.MeshGroupSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MeshGroupSystem()`  

```csharp
[Preserve]
	public MeshGroupSystem()
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

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdateQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<MeshGroup>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<BatchesUpdated>()
			}
		});
		m_AllQuery = GetEntityQuery(ComponentType.ReadOnly<MeshGroup>());
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityQuery query = (GetLoaded() ? m_AllQuery : m_UpdateQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			JobHandle dependency = JobChunkExtensions.ScheduleParallel(new SetMeshGroupsJob
			{
				m_PseudoRandomSeedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HumanType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Human_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MeshGroupType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Rendering_MeshGroup_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_MeshBatchType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Rendering_MeshBatch_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HumanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Human_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
				m_OverlayElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_OverlayElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_ActivityLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_RandomSeed = RandomSeed.Next()
			}, query, base.Dependency);
			base.Dependency = dependency;
		}
	}
```


## Nested types

- `Game.Rendering.MeshGroupSystem+SetMeshGroupsJob`  
- `Game.Rendering.MeshGroupSystem+TypeHandle`  

