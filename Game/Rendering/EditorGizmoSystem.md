# Game.Rendering.EditorGizmoSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EditorGizmoSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RenderQuery;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.EditorGizmoSystem+TypeHandle __TypeHandle;

    public EditorGizmoSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RenderQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderQuery;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.EditorGizmoSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.EditorGizmoSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EditorGizmoSystem()`  

```csharp
[Preserve]
	public EditorGizmoSystem()
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
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_RenderQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Tools.EditorContainer>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Hidden>());
		m_RenderingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<RenderingSettingsData>());
		RequireForUpdate(m_RenderQuery);
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
		if (!m_RenderingSystem.hideOverlay)
		{
			UnityEngine.Color hoveredColor = new UnityEngine.Color(0.5f, 0.5f, 1f, 1f);
			UnityEngine.Color errorColor = new UnityEngine.Color(1f, 0.5f, 0.5f, 1f);
			UnityEngine.Color warningColor = new UnityEngine.Color(1f, 1f, 0.5f, 1f);
			if (!m_RenderingSettingsQuery.IsEmptyIgnoreFilter)
			{
				RenderingSettingsData singleton = m_RenderingSettingsQuery.GetSingleton<RenderingSettingsData>();
				hoveredColor = singleton.m_HoveredColor;
				errorColor = singleton.m_ErrorColor;
				warningColor = singleton.m_WarningColor;
				hoveredColor.a = 1f;
				errorColor.a = 1f;
				warningColor.a = 1f;
			}
			JobHandle dependencies;
			JobHandle dependencies2;
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new EditorGizmoJob
			{
				m_NetNodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NetCurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ErrorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Error_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WarningType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Warning_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HighlightedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Highlighted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HoveredColor = hoveredColor,
				m_ErrorColor = errorColor,
				m_WarningColor = warningColor,
				m_CullingData = m_PreCullingSystem.GetCullingData(readOnly: true, out dependencies),
				m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies2)
			}, m_RenderQuery, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
			m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
			m_PreCullingSystem.AddCullingDataReader(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Rendering.EditorGizmoSystem+EditorGizmoJob`  
- `Game.Rendering.EditorGizmoSystem+TypeHandle`  

