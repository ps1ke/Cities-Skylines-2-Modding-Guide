# Game.Debug.ObjectDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_ObjectGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Debug.BaseDebugSystem+Option m_GeometryOption;
    private Game.Debug.BaseDebugSystem+Option m_MarkerOption;
    private Game.Debug.BaseDebugSystem+Option m_PivotOption;
    private Game.Debug.BaseDebugSystem+Option m_OutlineOption;
    private Game.Debug.BaseDebugSystem+Option m_InterpolatedOption;
    private Game.Debug.BaseDebugSystem+Option m_NetConnectionOption;
    private Game.Debug.BaseDebugSystem+Option m_GroupConnectionOption;
    private Game.Debug.BaseDebugSystem+Option m_DistrictOption;
    private Game.Debug.BaseDebugSystem+Option m_LotHeightOption;
    private Game.Debug.ObjectDebugSystem+TypeHandle __TypeHandle;

    public ObjectDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle DrawObjectGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ObjectGroup`  

```csharp
private Unity.Entities.EntityQuery m_ObjectGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_GeometryOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GeometryOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MarkerOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MarkerOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_PivotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PivotOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_OutlineOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_OutlineOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_InterpolatedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_InterpolatedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_NetConnectionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_NetConnectionOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_GroupConnectionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GroupConnectionOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_DistrictOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_DistrictOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LotHeightOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LotHeightOption;
```

- `private Game.Debug.ObjectDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.ObjectDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectDebugSystem()`  

```csharp
[Preserve]
	public ObjectDebugSystem()
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

- `private DrawObjectGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle DrawObjectGizmos(EntityQuery group, JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new ObjectGizmoJob
		{
			m_GeometryOption = m_GeometryOption.enabled,
			m_MarkerOption = m_MarkerOption.enabled,
			m_PivotOption = m_PivotOption.enabled,
			m_OutlineOption = m_OutlineOption.enabled,
			m_InterpolatedOption = m_InterpolatedOption.enabled,
			m_NetConnectionOption = m_NetConnectionOption.enabled,
			m_GroupConnectionOption = m_GroupConnectionOption.enabled,
			m_DistrictOption = m_DistrictOption.enabled,
			m_LotHeightOption = m_LotHeightOption.enabled,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AttachedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_ObjectGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnLocationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GroupMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingLotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Lot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetCurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Selected = m_ToolSystem.selected,
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, group, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_ObjectGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.Object>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Hidden>());
		m_GeometryOption = AddOption("Physical Objects", defaultEnabled: true);
		m_MarkerOption = AddOption("Marker Objects", defaultEnabled: true);
		m_PivotOption = AddOption("Draw Pivots", defaultEnabled: true);
		m_OutlineOption = AddOption("Draw Outlines", defaultEnabled: true);
		m_InterpolatedOption = AddOption("Interpolated Positions", defaultEnabled: true);
		m_NetConnectionOption = AddOption("Net Connections", defaultEnabled: true);
		m_GroupConnectionOption = AddOption("Group Connections", defaultEnabled: true);
		m_DistrictOption = AddOption("District Connections", defaultEnabled: false);
		m_LotHeightOption = AddOption("Lot Heights", defaultEnabled: false);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_ObjectGroup.IsEmptyIgnoreFilter)
		{
			base.Dependency = DrawObjectGizmos(m_ObjectGroup, base.Dependency);
		}
	}
```


## Nested types

- `Game.Debug.ObjectDebugSystem+ObjectGizmoJob`  
- `Game.Debug.ObjectDebugSystem+TypeHandle`  

