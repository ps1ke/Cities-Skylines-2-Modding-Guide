# Game.Rendering.BuildingLotRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingLotRenderSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Unity.Entities.EntityQuery m_LotQuery;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Game.Rendering.BuildingLotRenderSystem+TypeHandle __TypeHandle;

    public BuildingLotRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Unity.Entities.EntityQuery m_LotQuery`  

```csharp
private Unity.Entities.EntityQuery m_LotQuery;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Game.Rendering.BuildingLotRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BuildingLotRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BuildingLotRenderSystem()`  

```csharp
[Preserve]
	public BuildingLotRenderSystem()
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
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_OverlayRenderSystem = base.World.GetOrCreateSystemManaged<OverlayRenderSystem>();
		m_LotQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Temp>() },
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Extension>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Taxiway>(),
				ComponentType.ReadOnly<Tree>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Overridden>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Error>() },
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Extension>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Taxiway>(),
				ComponentType.ReadOnly<Tree>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Overridden>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Warning>() },
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Extension>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Taxiway>(),
				ComponentType.ReadOnly<Tree>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Overridden>()
			}
		});
		m_RenderingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<RenderingSettingsData>());
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
		Entity entity = (m_ToolSystem.actionMode.IsEditor() ? m_ToolSystem.selected : Entity.Null);
		bool flag = !m_LotQuery.IsEmptyIgnoreFilter;
		if (flag || !(entity == Entity.Null))
		{
			RenderingSettingsData renderingSettingsData = new RenderingSettingsData
			{
				m_HoveredColor = new UnityEngine.Color(0.5f, 0.5f, 1f, 1f),
				m_ErrorColor = new UnityEngine.Color(1f, 0.5f, 0.5f, 1f),
				m_WarningColor = new UnityEngine.Color(1f, 1f, 0.5f, 1f),
				m_OwnerColor = new UnityEngine.Color(0.5f, 1f, 0.5f, 1f)
			};
			if (!m_RenderingSettingsQuery.IsEmptyIgnoreFilter)
			{
				RenderingSettingsData singleton = m_RenderingSettingsQuery.GetSingleton<RenderingSettingsData>();
				renderingSettingsData.m_HoveredColor = singleton.m_HoveredColor;
				renderingSettingsData.m_ErrorColor = singleton.m_ErrorColor;
				renderingSettingsData.m_WarningColor = singleton.m_WarningColor;
				renderingSettingsData.m_OwnerColor = singleton.m_OwnerColor;
			}
			JobHandle dependencies;
			OverlayRenderSystem.Buffer buffer = m_OverlayRenderSystem.GetBuffer(out dependencies);
			base.Dependency = JobHandle.CombineDependencies(base.Dependency, dependencies);
			if (flag)
			{
				bool zonesVisible = m_ToolSystem.activeTool != null && m_ToolSystem.activeTool.requireZones;
				BuildingLotRenderJob jobData = new BuildingLotRenderJob
				{
					m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ExtensionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Extension_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_AssetStampType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_AssetStamp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TreeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_StartGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EndGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_WarningType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Warning_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ErrorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Error_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabBuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabAssetStampData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AssetStampData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabServiceUpgradeBuildings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeBuilding_RO_BufferLookup, ref base.CheckedStateRef),
					m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
					m_ZonesVisible = zonesVisible,
					m_RenderingSettingsData = renderingSettingsData,
					m_OverlayBuffer = buffer
				};
				base.Dependency = JobChunkExtensions.Schedule(jobData, m_LotQuery, base.Dependency);
			}
			if (entity != Entity.Null)
			{
				BuildingTerraformRenderJob jobData2 = new BuildingTerraformRenderJob
				{
					m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabBuildingTerraformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingTerraformData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabAdditionalTerraform = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AdditionalBuildingTerraformElement_RO_BufferLookup, ref base.CheckedStateRef),
					m_Selected = entity,
					m_OverlayBuffer = buffer
				};
				base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
			}
			m_OverlayRenderSystem.AddBufferWriter(base.Dependency);
		}
	}
```


## Nested types

- `Game.Rendering.BuildingLotRenderSystem+BuildingLotRenderJob`  
- `Game.Rendering.BuildingLotRenderSystem+BuildingTerraformRenderJob`  
- `Game.Rendering.BuildingLotRenderSystem+TypeHandle`  

