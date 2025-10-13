# Game.Rendering.GuideLinesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GuideLinesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_MarkerNodeQuery;
    private Unity.Entities.EntityQuery m_TempNodeQuery;
    private Unity.Entities.EntityQuery m_WaterSourceQuery;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.RouteToolSystem m_RouteToolSystem;
    private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
    private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.WaterToolSystem m_WaterToolSystem;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Collections.NativeList<System.Boolean> m_AngleSides;
    private Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo> m_Tooltips;
    private Unity.Jobs.JobHandle m_TooltipDeps;
    private Game.Rendering.GuideLinesSystem+TypeHandle __TypeHandle;

    public GuideLinesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void CheckDirection(Unity.Mathematics.float2 startDir, Unity.Mathematics.float2 checkDir, Unity.Mathematics.float2& leftDir, Unity.Mathematics.float2& rightDir, System.Int32& bestLeft, System.Int32& bestRight, Unity.Mathematics.float2& leftDir2, Unity.Mathematics.float2& rightDir2, System.Int32& bestLeft2, System.Int32& bestRight2);
    private static System.Void DrawAngleIndicator(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo> tooltips, Game.Prefabs.GuideLineSettingsData guideLineSettings, Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Mathematics.float2 dir1, Unity.Mathematics.float2 dir2, System.Single size, System.Single lineWidth, System.Int32 angle, System.Boolean angleSide);
    private static System.Void DrawAreaRange(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position, Game.Prefabs.LotData lotData);
    private static System.Void DrawNetCourse(Game.Rendering.OverlayRenderSystem+Buffer buffer, Game.Tools.NetCourse netCourse, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData, Game.Prefabs.NetGeometryData netGeometryData, Game.Prefabs.GuideLineSettingsData guideLineSettings);
    private static System.Void DrawNetCourse(Game.Rendering.OverlayRenderSystem+Buffer buffer, Game.Tools.NetCourse netCourse, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Game.Prefabs.NetGeometryData netGeometryData, Game.Prefabs.GuideLineSettingsData guideLineSettings);
    private static System.Void DrawUpgradeRange(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position, Game.Prefabs.GuideLineSettingsData guideLineSettings, Game.Prefabs.BuildingData ownerBuildingData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ServiceUpgradeData serviceUpgradeData);
    public Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo> GetTooltips(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_MarkerNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_MarkerNodeQuery;
```

- `private Unity.Entities.EntityQuery m_TempNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempNodeQuery;
```

- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterSourceQuery;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  

```csharp
private Game.Tools.RouteToolSystem m_RouteToolSystem;
```

- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  

```csharp
private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
```

- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  

```csharp
private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.WaterToolSystem m_WaterToolSystem`  

```csharp
private Game.Tools.WaterToolSystem m_WaterToolSystem;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Collections.NativeList<System.Boolean> m_AngleSides`  

```csharp
private Unity.Collections.NativeList<System.Boolean> m_AngleSides;
```

- `private Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo> m_Tooltips`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo> m_Tooltips;
```

- `private Unity.Jobs.JobHandle m_TooltipDeps`  

```csharp
private Unity.Jobs.JobHandle m_TooltipDeps;
```

- `private Game.Rendering.GuideLinesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.GuideLinesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GuideLinesSystem()`  

```csharp
[Preserve]
	public GuideLinesSystem()
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

- `private static CheckDirection(Unity.Mathematics.float2 startDir, Unity.Mathematics.float2 checkDir, Unity.Mathematics.float2& leftDir, Unity.Mathematics.float2& rightDir, System.Int32& bestLeft, System.Int32& bestRight, Unity.Mathematics.float2& leftDir2, Unity.Mathematics.float2& rightDir2, System.Int32& bestLeft2, System.Int32& bestRight2) : System.Void`  

```csharp
private static void CheckDirection(float2 startDir, float2 checkDir, ref float2 leftDir, ref float2 rightDir, ref int bestLeft, ref int bestRight, ref float2 leftDir2, ref float2 rightDir2, ref int bestLeft2, ref int bestRight2)
	{
		if (!MathUtils.TryNormalize(ref checkDir))
		{
			return;
		}
		int num = Mathf.RoundToInt(math.degrees(math.acos(math.clamp(math.dot(startDir, checkDir), -1f, 1f))));
		if (num == 0)
		{
			return;
		}
		bool num2 = math.dot(MathUtils.Right(startDir), checkDir) > 0f;
		if (num2 || num == 180)
		{
			if (num < bestRight)
			{
				rightDir = checkDir;
				bestRight = num;
			}
			if ((num == 90 || num == 180) && num < bestRight2)
			{
				rightDir2 = checkDir;
				bestRight2 = num;
			}
		}
		if (!num2 || num == 180)
		{
			if (num < bestLeft)
			{
				leftDir = checkDir;
				bestLeft = num;
			}
			if ((num == 90 || num == 180) && num < bestLeft2)
			{
				leftDir2 = checkDir;
				bestLeft2 = num;
			}
		}
	}
```

- `private static DrawAngleIndicator(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo> tooltips, Game.Prefabs.GuideLineSettingsData guideLineSettings, Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Mathematics.float2 dir1, Unity.Mathematics.float2 dir2, System.Single size, System.Single lineWidth, System.Int32 angle, System.Boolean angleSide) : System.Void`  

```csharp
private static void DrawAngleIndicator(OverlayRenderSystem.Buffer buffer, NativeList<TooltipInfo> tooltips, GuideLineSettingsData guideLineSettings, Line3.Segment line1, Line3.Segment line2, float2 dir1, float2 dir2, float size, float lineWidth, int angle, bool angleSide)
	{
		if (angle == 180)
		{
			float2 @float = (angleSide ? MathUtils.Right(dir1) : MathUtils.Left(dir1));
			float2 float2 = (angleSide ? MathUtils.Right(dir2) : MathUtils.Left(dir2));
			float3 b = line1.b;
			b.xz -= dir1 * size;
			float3 b2 = line1.b;
			float3 b3 = line1.b;
			b2.xz += @float * (size - lineWidth * 0.5f) - dir1 * size;
			b3.xz += @float * size - dir1 * (size + lineWidth * 0.5f);
			float3 a = line2.a;
			float3 a2 = line2.a;
			a.xz -= float2 * size + dir2 * (size + lineWidth * 0.5f);
			a2.xz -= float2 * (size - lineWidth * 0.5f) + dir2 * size;
			float3 a3 = line2.a;
			a3.xz -= dir2 * size;
			buffer.DrawLine(guideLineSettings.m_HighPriorityColor, new Line3.Segment(b, b2), lineWidth);
			buffer.DrawLine(guideLineSettings.m_HighPriorityColor, new Line3.Segment(b3, a), lineWidth);
			buffer.DrawLine(guideLineSettings.m_HighPriorityColor, new Line3.Segment(a2, a3), lineWidth);
			float3 b4 = line1.b;
			b4.xz += @float * (size * 1.5f);
			tooltips.Add(new TooltipInfo(TooltipType.Angle, b4, angle));
		}
		else if (angle > 90)
		{
			float2 float3 = math.normalize(dir1 + dir2);
			float3 b5 = line1.b;
			b5.xz -= dir1 * size;
			float3 startTangent = new float3
			{
				xz = (angleSide ? MathUtils.Right(dir1) : MathUtils.Left(dir1))
			};
			float3 b6 = line1.b;
			b6.xz -= float3 * size;
			float3 float4 = new float3
			{
				xz = (angleSide ? MathUtils.Right(float3) : MathUtils.Left(float3))
			};
			float3 a4 = line2.a;
			a4.xz -= dir2 * size;
			float3 endTangent = new float3
			{
				xz = (angleSide ? MathUtils.Right(dir2) : MathUtils.Left(dir2))
			};
			buffer.DrawCurve(guideLineSettings.m_HighPriorityColor, NetUtils.FitCurve(b5, startTangent, float4, b6), lineWidth);
			buffer.DrawCurve(guideLineSettings.m_HighPriorityColor, NetUtils.FitCurve(b6, float4, endTangent, a4), lineWidth);
			float3 b7 = line1.b;
			b7.xz -= float3 * (size * 1.5f);
			tooltips.Add(new TooltipInfo(TooltipType.Angle, b7, angle));
		}
		else if (angle == 90)
		{
			float3 b8 = line1.b;
			b8.xz -= dir1 * size;
			float3 b9 = line1.b;
			float3 b10 = line1.b;
			b9.xz -= dir2 * (size - lineWidth * 0.5f) + dir1 * size;
			b10.xz -= dir2 * size + dir1 * (size + lineWidth * 0.5f);
			float3 a5 = line2.a;
			a5.xz -= dir2 * size;
			buffer.DrawLine(guideLineSettings.m_HighPriorityColor, new Line3.Segment(b8, b9), lineWidth);
			buffer.DrawLine(guideLineSettings.m_HighPriorityColor, new Line3.Segment(b10, a5), lineWidth);
			float3 b11 = line1.b;
			b11.xz -= math.normalizesafe(dir1 + dir2) * (size * 1.5f);
			tooltips.Add(new TooltipInfo(TooltipType.Angle, b11, angle));
		}
		else if (angle > 0)
		{
			float3 b12 = line1.b;
			b12.xz -= dir1 * size;
			float3 startTangent2 = new float3
			{
				xz = (angleSide ? MathUtils.Right(dir1) : MathUtils.Left(dir1))
			};
			float3 a6 = line2.a;
			a6.xz -= dir2 * size;
			float3 endTangent2 = new float3
			{
				xz = (angleSide ? MathUtils.Right(dir2) : MathUtils.Left(dir2))
			};
			buffer.DrawCurve(guideLineSettings.m_HighPriorityColor, NetUtils.FitCurve(b12, startTangent2, endTangent2, a6), lineWidth);
			float3 b13 = line1.b;
			b13.xz -= math.normalizesafe(dir1 + dir2) * (size * 1.5f);
			tooltips.Add(new TooltipInfo(TooltipType.Angle, b13, angle));
		}
	}
```

- `private static DrawAreaRange(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position, Game.Prefabs.LotData lotData) : System.Void`  

```csharp
private static void DrawAreaRange(OverlayRenderSystem.Buffer buffer, quaternion rotation, float3 position, LotData lotData)
	{
		float3 @float = math.forward(rotation);
		UnityEngine.Color color = lotData.m_RangeColor;
		UnityEngine.Color fillColor = color;
		fillColor.a = 0f;
		OverlayRenderSystem.StyleFlags styleFlags = ((!lotData.m_OnWater) ? OverlayRenderSystem.StyleFlags.Projected : ((OverlayRenderSystem.StyleFlags)0));
		buffer.DrawCircle(color, fillColor, lotData.m_MaxRadius * 0.02f, styleFlags, @float.xz, position, lotData.m_MaxRadius * 2f);
	}
```

- `private static DrawNetCourse(Game.Rendering.OverlayRenderSystem+Buffer buffer, Game.Tools.NetCourse netCourse, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData, Game.Prefabs.NetGeometryData netGeometryData, Game.Prefabs.GuideLineSettingsData guideLineSettings) : System.Void`  

```csharp
private static void DrawNetCourse(OverlayRenderSystem.Buffer buffer, NetCourse netCourse, OverlayRenderSystem.StyleFlags styleFlags, NetGeometryData netGeometryData, GuideLineSettingsData guideLineSettings)
	{
		math.select(0f, 1f, new bool2((netCourse.m_StartPosition.m_Flags & (CoursePosFlags.IsFirst | CoursePosFlags.IsLast)) != 0, (netCourse.m_EndPosition.m_Flags & (CoursePosFlags.IsFirst | CoursePosFlags.IsLast)) != 0));
	}
```

- `private static DrawNetCourse(Game.Rendering.OverlayRenderSystem+Buffer buffer, Game.Tools.NetCourse netCourse, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Game.Prefabs.NetGeometryData netGeometryData, Game.Prefabs.GuideLineSettingsData guideLineSettings) : System.Void`  

```csharp
private static void DrawNetCourse(OverlayRenderSystem.Buffer buffer, NetCourse netCourse, OverlayRenderSystem.StyleFlags styleFlags, NetGeometryData netGeometryData, GuideLineSettingsData guideLineSettings)
	{
		math.select(0f, 1f, new bool2((netCourse.m_StartPosition.m_Flags & (CoursePosFlags.IsFirst | CoursePosFlags.IsLast)) != 0, (netCourse.m_EndPosition.m_Flags & (CoursePosFlags.IsFirst | CoursePosFlags.IsLast)) != 0));
	}
```

- `private static DrawUpgradeRange(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position, Game.Prefabs.GuideLineSettingsData guideLineSettings, Game.Prefabs.BuildingData ownerBuildingData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ServiceUpgradeData serviceUpgradeData) : System.Void`  

```csharp
private static void DrawUpgradeRange(OverlayRenderSystem.Buffer buffer, quaternion rotation, float3 position, GuideLineSettingsData guideLineSettings, BuildingData ownerBuildingData, BuildingData buildingData, ServiceUpgradeData serviceUpgradeData)
	{
		UnityEngine.Color lowPriorityColor = guideLineSettings.m_LowPriorityColor;
		UnityEngine.Color fillColor = lowPriorityColor;
		fillColor.a = 0f;
		BuildingUtils.CalculateUpgradeRangeValues(rotation, ownerBuildingData, buildingData, serviceUpgradeData, out var forward, out var width, out var length, out var roundness, out var circular);
		roundness *= 2f;
		length -= roundness;
		roundness /= width;
		if (circular)
		{
			buffer.DrawCircle(lowPriorityColor, fillColor, width * 0.01f, OverlayRenderSystem.StyleFlags.Projected, forward.xz, position, width);
		}
		else
		{
			buffer.DrawLine(line: new Line3.Segment(position - forward * (length * 0.5f), position + forward * (length * 0.5f)), outlineColor: lowPriorityColor, fillColor: fillColor, outlineWidth: width * 0.01f, styleFlags: OverlayRenderSystem.StyleFlags.Projected, width: width, roundness: roundness);
		}
	}
```

- `public GetTooltips(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo>`  

```csharp
public NativeList<TooltipInfo> GetTooltips(out JobHandle dependencies)
	{
		dependencies = m_TooltipDeps;
		return m_Tooltips;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_NetToolSystem = base.World.GetOrCreateSystemManaged<NetToolSystem>();
		m_RouteToolSystem = base.World.GetOrCreateSystemManaged<RouteToolSystem>();
		m_ZoneToolSystem = base.World.GetOrCreateSystemManaged<ZoneToolSystem>();
		m_SelectionToolSystem = base.World.GetOrCreateSystemManaged<SelectionToolSystem>();
		m_AreaToolSystem = base.World.GetOrCreateSystemManaged<AreaToolSystem>();
		m_ObjectToolSystem = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
		m_WaterToolSystem = base.World.GetOrCreateSystemManaged<WaterToolSystem>();
		m_OverlayRenderSystem = base.World.GetOrCreateSystemManaged<OverlayRenderSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_DefinitionQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<CreationDefinition>() },
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<NetCourse>(),
				ComponentType.ReadOnly<WaypointDefinition>(),
				ComponentType.ReadOnly<Zoning>(),
				ComponentType.ReadOnly<Game.Areas.Node>(),
				ComponentType.ReadOnly<ObjectDefinition>()
			},
			None = new ComponentType[0]
		});
		m_TempNodeQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.Node>(), ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Deleted>());
		m_MarkerNodeQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.Marker>(), ComponentType.ReadOnly<Orphan>(), ComponentType.ReadOnly<Game.Net.Node>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_WaterSourceQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Simulation.WaterSourceData>(), ComponentType.Exclude<PrefabRef>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_RenderingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<GuideLineSettingsData>());
		m_AngleSides = new NativeList<bool>(4, Allocator.Persistent);
		m_Tooltips = new NativeList<TooltipInfo>(8, Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_AngleSides.Dispose();
		m_Tooltips.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_Tooltips.Clear();
		bool flag = (m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) != 0;
		if (m_ToolSystem.activeTool == m_NetToolSystem)
		{
			if (flag)
			{
				return;
			}
			JobHandle outJobHandle;
			JobHandle dependencies;
			JobHandle dependencies2;
			JobHandle deps;
			JobHandle dependencies3;
			NetToolGuideLinesJob jobData = new NetToolGuideLinesJob
			{
				m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_NetCourseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_NetCourse_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ConnectedEdgeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PlaceableNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ElectricityConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterPipeConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterPipeConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
				m_DefinitionChunks = m_DefinitionQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_ControlPoints = m_NetToolSystem.GetControlPoints(out dependencies),
				m_SnapLines = m_NetToolSystem.GetSnapLines(out dependencies2),
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
				m_Mode = m_NetToolSystem.actualMode,
				m_HighlightVoltage = Game.Prefabs.ElectricityConnection.Voltage.Invalid,
				m_HighlightWater = false,
				m_HighResourceLine = false,
				m_Prefab = ((m_NetToolSystem.prefab != null) ? m_PrefabSystem.GetEntity(m_NetToolSystem.prefab) : Entity.Null),
				m_GuideLineSettingsData = m_RenderingSettingsQuery.GetSingleton<GuideLineSettingsData>(),
				m_AngleSides = m_AngleSides,
				m_Tooltips = m_Tooltips,
				m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies3)
			};
			JobHandle jobHandle = JobUtils.CombineDependencies(dependencies, dependencies2, deps, dependencies3);
			if (m_NetToolSystem.prefab is PowerLinePrefab)
			{
				if (m_NetToolSystem.prefab.TryGet<Game.Prefabs.ElectricityConnection>(out var component))
				{
					jobData.m_MarkerNodeChunks = m_MarkerNodeQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out var outJobHandle2);
					jobData.m_TempNodeChunks = m_TempNodeQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out var outJobHandle3);
					jobData.m_HighlightVoltage = component.m_Voltage;
					jobHandle = JobHandle.CombineDependencies(jobHandle, outJobHandle2, outJobHandle3);
				}
			}
			else if (m_NetToolSystem.prefab is PipelinePrefab)
			{
				jobData.m_MarkerNodeChunks = m_MarkerNodeQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out var outJobHandle4);
				jobData.m_TempNodeChunks = m_TempNodeQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out var outJobHandle5);
				jobHandle = JobHandle.CombineDependencies(jobHandle, outJobHandle4, outJobHandle5);
				if (m_NetToolSystem.prefab.TryGet<Game.Prefabs.WaterPipeConnection>(out var component2))
				{
					jobData.m_HighlightWater.x = component2.m_FreshCapacity > 0;
					jobData.m_HighlightWater.y = component2.m_SewageCapacity > 0;
				}
				else
				{
					jobData.m_HighResourceLine = true;
				}
			}
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle, jobHandle));
			if (jobData.m_MarkerNodeChunks.IsCreated)
			{
				jobData.m_MarkerNodeChunks.Dispose(jobHandle2);
			}
			if (jobData.m_TempNodeChunks.IsCreated)
			{
				jobData.m_TempNodeChunks.Dispose(jobHandle2);
			}
			jobData.m_DefinitionChunks.Dispose(jobHandle2);
			m_TerrainSystem.AddCPUHeightReader(jobHandle2);
			m_WaterSystem.AddSurfaceReader(jobHandle2);
			m_OverlayRenderSystem.AddBufferWriter(jobHandle2);
			m_TooltipDeps = jobHandle2;
			base.Dependency = jobHandle2;
		}
		else if (m_ToolSystem.activeTool == m_RouteToolSystem)
		{
			if (!flag)
			{
				JobHandle outJobHandle6;
				JobHandle dependencies4;
				JobHandle dependencies5;
				RouteToolGuideLinesJob jobData2 = new RouteToolGuideLinesJob
				{
					m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_WaypointDefinitionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_WaypointDefinition_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_RouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Route_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_DefinitionChunks = m_DefinitionQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle6),
					m_ControlPoints = m_RouteToolSystem.GetControlPoints(out dependencies4),
					m_MoveStartPosition = m_RouteToolSystem.moveStartPosition,
					m_State = m_RouteToolSystem.state,
					m_GuideLineSettingsData = m_RenderingSettingsQuery.GetSingleton<GuideLineSettingsData>(),
					m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies5)
				};
				JobHandle job = JobHandle.CombineDependencies(dependencies4, dependencies5);
				JobHandle jobHandle3 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, outJobHandle6, job));
				jobData2.m_DefinitionChunks.Dispose(jobHandle3);
				m_OverlayRenderSystem.AddBufferWriter(jobHandle3);
				base.Dependency = jobHandle3;
			}
		}
		else if (m_ToolSystem.activeTool == m_ZoneToolSystem)
		{
			if (!flag)
			{
				JobHandle outJobHandle7;
				JobHandle dependencies6;
				ZoneToolGuideLinesJob jobData3 = new ZoneToolGuideLinesJob
				{
					m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ZoningType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Zoning_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_DefinitionChunks = m_DefinitionQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle7),
					m_GuideLineSettingsData = m_RenderingSettingsQuery.GetSingleton<GuideLineSettingsData>(),
					m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies6)
				};
				JobHandle jobHandle4 = IJobExtensions.Schedule(jobData3, JobHandle.CombineDependencies(base.Dependency, outJobHandle7, dependencies6));
				jobData3.m_DefinitionChunks.Dispose(jobHandle4);
				m_OverlayRenderSystem.AddBufferWriter(jobHandle4);
				base.Dependency = jobHandle4;
			}
		}
		else if (m_ToolSystem.activeTool == m_SelectionToolSystem)
		{
			if (!flag)
			{
				Quad3 quad;
				bool selectionQuad = m_SelectionToolSystem.GetSelectionQuad(out quad);
				JobHandle dependencies7;
				JobHandle jobHandle5 = IJobExtensions.Schedule(new SelectionToolGuideLinesJob
				{
					m_State = m_SelectionToolSystem.state,
					m_SelectionType = m_SelectionToolSystem.selectionType,
					m_SelectionQuadIsValid = selectionQuad,
					m_SelectionQuad = quad,
					m_GuideLineSettingsData = m_RenderingSettingsQuery.GetSingleton<GuideLineSettingsData>(),
					m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies7)
				}, JobHandle.CombineDependencies(base.Dependency, dependencies7));
				m_OverlayRenderSystem.AddBufferWriter(jobHandle5);
				base.Dependency = jobHandle5;
			}
		}
		else if (m_ToolSystem.activeTool == m_AreaToolSystem)
		{
			if (!flag)
			{
				JobHandle outJobHandle8;
				NativeList<ControlPoint> moveStartPositions;
				JobHandle dependencies8;
				JobHandle dependencies9;
				AreaToolGuideLinesJob jobData4 = new AreaToolGuideLinesJob
				{
					m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabLotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LotData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
					m_DefinitionChunks = m_DefinitionQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle8),
					m_ControlPoints = m_AreaToolSystem.GetControlPoints(out moveStartPositions, out dependencies8),
					m_MoveStartPositions = moveStartPositions,
					m_State = m_AreaToolSystem.state,
					m_Prefab = ((m_AreaToolSystem.prefab != null) ? m_PrefabSystem.GetEntity(m_AreaToolSystem.prefab) : Entity.Null),
					m_GuideLineSettingsData = m_RenderingSettingsQuery.GetSingleton<GuideLineSettingsData>(),
					m_AngleSides = m_AngleSides,
					m_Tooltips = m_Tooltips,
					m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies9)
				};
				JobHandle job2 = JobHandle.CombineDependencies(dependencies8, dependencies9);
				JobHandle jobHandle6 = IJobExtensions.Schedule(jobData4, JobHandle.CombineDependencies(base.Dependency, outJobHandle8, job2));
				jobData4.m_DefinitionChunks.Dispose(jobHandle6);
				m_OverlayRenderSystem.AddBufferWriter(jobHandle6);
				m_TooltipDeps = jobHandle6;
				base.Dependency = jobHandle6;
			}
		}
		else if (m_ToolSystem.activeTool == m_ObjectToolSystem)
		{
			if (!flag)
			{
				JobHandle outJobHandle9;
				JobHandle dependencies10;
				JobHandle dependencies11;
				JobHandle deps2;
				JobHandle dependencies12;
				JobHandle dependencies13;
				ObjectToolGuideLinesJob jobData5 = new ObjectToolGuideLinesJob
				{
					m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ObjectDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_ObjectDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OwnerDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_OwnerDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NetCourseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_NetCourse_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabPlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabLotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LotData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabPlaceableNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabSubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
					m_PrefabSubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
					m_DefinitionChunks = m_DefinitionQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle9),
					m_ControlPoints = m_ObjectToolSystem.GetControlPoints(out dependencies10),
					m_SubSnapPoints = m_ObjectToolSystem.GetSubSnapPoints(out dependencies11),
					m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
					m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps2),
					m_NetUpgradeState = m_ObjectToolSystem.GetNetUpgradeStates(out dependencies12),
					m_GuideLineSettingsData = m_RenderingSettingsQuery.GetSingleton<GuideLineSettingsData>(),
					m_Mode = m_ObjectToolSystem.actualMode,
					m_State = m_ObjectToolSystem.state,
					m_Prefab = ((m_ObjectToolSystem.prefab != null) ? m_PrefabSystem.GetEntity(m_ObjectToolSystem.prefab) : Entity.Null),
					m_DistanceScale = m_ObjectToolSystem.distanceScale,
					m_AngleSides = m_AngleSides,
					m_Tooltips = m_Tooltips,
					m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies13)
				};
				JobHandle jobHandle7 = IJobExtensions.Schedule(jobData5, JobUtils.CombineDependencies(base.Dependency, outJobHandle9, dependencies10, dependencies11, deps2, dependencies12, dependencies13));
				jobData5.m_DefinitionChunks.Dispose(jobHandle7);
				m_TerrainSystem.AddCPUHeightReader(jobHandle7);
				m_WaterSystem.AddSurfaceReader(jobHandle7);
				m_OverlayRenderSystem.AddBufferWriter(jobHandle7);
				m_TooltipDeps = jobHandle7;
				base.Dependency = jobHandle7;
			}
		}
		else if (m_ToolSystem.activeTool == m_WaterToolSystem)
		{
			float3 cameraRight = default(float3);
			if (m_CameraUpdateSystem.TryGetViewer(out var viewer))
			{
				cameraRight = viewer.right;
			}
			JobHandle outJobHandle10;
			JobHandle dependencies14;
			WaterToolGuideLinesJob jobData6 = new WaterToolGuideLinesJob
			{
				m_WaterSourceDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterSourceData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_GuideLineSettingsData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GuideLineSettingsData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterSourceColors = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_WaterSourceColorElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Attribute = m_WaterToolSystem.attribute,
				m_PositionOffset = m_TerrainSystem.positionOffset,
				m_CameraRight = cameraRight,
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_WaterSourceChunks = m_WaterSourceQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle10),
				m_GuideLineSettingsEntity = m_RenderingSettingsQuery.GetSingletonEntity(),
				m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies14)
			};
			JobHandle jobHandle8 = IJobExtensions.Schedule(jobData6, JobHandle.CombineDependencies(base.Dependency, outJobHandle10, dependencies14));
			jobData6.m_WaterSourceChunks.Dispose(jobHandle8);
			m_OverlayRenderSystem.AddBufferWriter(jobHandle8);
			base.Dependency = jobHandle8;
		}
	}
```


## Nested types

- `Game.Rendering.GuideLinesSystem+TooltipInfo`  
- `Game.Rendering.GuideLinesSystem+TooltipType`  
- `Game.Rendering.GuideLinesSystem+WaterToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+ObjectToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+AreaToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+SelectionToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+ZoneToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+RouteToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+NetToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+TypeHandle`  

