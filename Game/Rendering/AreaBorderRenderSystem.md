# Game.Rendering.AreaBorderRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaBorderRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_AreaBorderQuery;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Game.Rendering.AreaBorderRenderSystem+TypeHandle __TypeHandle;

    public AreaBorderRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_AreaBorderQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaBorderQuery;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Game.Rendering.AreaBorderRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AreaBorderRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaBorderRenderSystem()`  

```csharp
[Preserve]
	public AreaBorderRenderSystem()
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
		m_OverlayRenderSystem = base.World.GetOrCreateSystemManaged<OverlayRenderSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_AreaBorderQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Area>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Error>(),
				ComponentType.ReadOnly<Warning>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_RenderingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<RenderingSettingsData>());
		RequireForUpdate(m_AreaBorderQuery);
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
		RenderingSettingsData renderingSettingsData = new RenderingSettingsData
		{
			m_HoveredColor = new Color(0.5f, 0.5f, 1f, 0.5f),
			m_ErrorColor = new Color(1f, 0.25f, 0.25f, 0.5f),
			m_WarningColor = new Color(1f, 1f, 0.25f, 0.5f),
			m_OwnerColor = new Color(0.5f, 1f, 0.5f, 0.5f)
		};
		if (!m_RenderingSettingsQuery.IsEmptyIgnoreFilter)
		{
			RenderingSettingsData singleton = m_RenderingSettingsQuery.GetSingleton<RenderingSettingsData>();
			renderingSettingsData.m_HoveredColor = singleton.m_HoveredColor;
			renderingSettingsData.m_ErrorColor = singleton.m_ErrorColor;
			renderingSettingsData.m_WarningColor = singleton.m_WarningColor;
			renderingSettingsData.m_OwnerColor = singleton.m_OwnerColor;
		}
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_AreaBorderQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle dependencies;
		JobHandle jobHandle = IJobExtensions.Schedule(new AreaBorderRenderJob
		{
			m_AreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Area_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MapTileType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_MapTile_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WarningType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Warning_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ErrorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Error_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RenderingSettingsData = renderingSettingsData,
			m_Chunks = chunks,
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies)
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle, dependencies));
		chunks.Dispose(jobHandle);
		m_OverlayRenderSystem.AddBufferWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Rendering.AreaBorderRenderSystem+Border`  
- `Game.Rendering.AreaBorderRenderSystem+AreaBorderRenderJob`  
- `Game.Rendering.AreaBorderRenderSystem+TypeHandle`  

