# Game.Areas.GeometrySystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GeometrySystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
    private Unity.Entities.EntityQuery m_AllAreasQuery;
    private Unity.Entities.EntityQuery m_CreatedBuildingsQuery;
    private System.Boolean m_Loaded;
    private Game.Areas.GeometrySystem+TypeHandle __TypeHandle;

    public GeometrySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single Area(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
    public static System.Single Area(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes);
    public static System.Void BuildEdgeBounds(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeArray<Unity.Mathematics.float3> expandedNodes, Unity.Collections.NativeArray`1[[Colossal.Mathematics.Bounds2, Colossal.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeBounds, System.Int32& totalDepth);
    public static System.Void EqualizeTriangles<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles);
    private static System.Single GetEqualizationValue(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.Triangle triangle);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private static System.Boolean Snip(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.GeometrySystem+Index index0, Game.Areas.GeometrySystem+Index index1, Game.Areas.GeometrySystem+Index index2, System.Int32 nodeCount, System.Int32 totalDepth, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, Unity.Collections.NativeArray<Game.Areas.GeometrySystem+Index> indexBuffer);
    public System.Void TerrainHeightsReadyAfterLoading();
    public static System.Void Triangulate<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, System.Int32 totalDepth, System.Boolean isCounterClockwise);
    private static System.Boolean TurnEdgeIfNeeded<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, Unity.Mathematics.int2> edgeMap, Unity.Mathematics.int2 index1, Unity.Mathematics.int2 index2);
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
```

- `private Unity.Entities.EntityQuery m_AllAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllAreasQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedBuildingsQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Areas.GeometrySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.GeometrySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GeometrySystem()`  

```csharp
[Preserve]
	public GeometrySystem()
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

- `public static Area(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : System.Single`  

```csharp
public static float Area(NativeArray<SubAreaNode> nodes)
	{
		int length = nodes.Length;
		float num = 0f;
		float3 @float = 0f;
		if (nodes.Length != 0)
		{
			@float = nodes[0].m_Position;
		}
		int index = length - 1;
		int num2 = 0;
		while (num2 < length)
		{
			float2 float2 = (nodes[index].m_Position.xz - @float.xz) * (nodes[num2].m_Position.zx - @float.zx);
			num += float2.x - float2.y;
			index = num2++;
		}
		return num * 0.5f;
	}
```

- `public static Area(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes) : System.Single`  

```csharp
public static float Area(NativeArray<SubAreaNode> nodes)
	{
		int length = nodes.Length;
		float num = 0f;
		float3 @float = 0f;
		if (nodes.Length != 0)
		{
			@float = nodes[0].m_Position;
		}
		int index = length - 1;
		int num2 = 0;
		while (num2 < length)
		{
			float2 float2 = (nodes[index].m_Position.xz - @float.xz) * (nodes[num2].m_Position.zx - @float.zx);
			num += float2.x - float2.y;
			index = num2++;
		}
		return num * 0.5f;
	}
```

- `public static BuildEdgeBounds(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeArray<Unity.Mathematics.float3> expandedNodes, Unity.Collections.NativeArray`1[[Colossal.Mathematics.Bounds2, Colossal.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeBounds, System.Int32& totalDepth) : System.Void`  

```csharp
public static void BuildEdgeBounds(DynamicBuffer<Node> nodes, NativeArray<float3> expandedNodes, out NativeArray<Bounds2> edgeBounds, out int totalDepth)
	{
		int num = -1;
		int num2 = 0;
		int num3;
		for (num3 = nodes.Length; num3 >= 4; num3 >>= 1)
		{
			num += 1 << num2++;
		}
		edgeBounds = new NativeArray<Bounds2>(num, Allocator.Temp);
		num2 = (totalDepth = num2 - 1);
		int num4 = 1 << num2;
		int num5 = num - num4;
		num3 = nodes.Length;
		for (int i = 0; i < num4; i++)
		{
			int num6 = i * num3 >> num2;
			int num7 = (i + 1) * num3 >> num2;
			Bounds2 value = MathUtils.Bounds(nodes[num6].m_Position.xz, expandedNodes[num6].xz);
			num6++;
			for (int j = num6; j <= num7; j++)
			{
				int index = math.select(j, 0, j == num3);
				value |= nodes[index].m_Position.xz;
				value |= expandedNodes[index].xz;
			}
			edgeBounds[num5 + i] = value;
		}
		while (--num2 > 0)
		{
			int num8 = num5;
			num4 = 1 << num2;
			num5 -= num4;
			for (int k = 0; k < num4; k++)
			{
				edgeBounds[num5 + k] = edgeBounds[num8 + (k << 1)] | edgeBounds[num8 + (k << 1) + 1];
			}
		}
	}
```

- `public static EqualizeTriangles<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles) : System.Void`  

```csharp
public static System.Void EqualizeTriangles<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles);
```

- `private static GetEqualizationValue(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.Triangle triangle) : System.Single`  

```csharp
private static float GetEqualizationValue(NativeArray<float3> nodes, Triangle triangle)
	{
		Triangle2 triangle2 = new Triangle2(nodes[triangle.m_Indices.x].xz, nodes[triangle.m_Indices.y].xz, nodes[triangle.m_Indices.z].xz);
		float3 @float = new float3(triangle2.a.x, triangle2.b.x, triangle2.c.x);
		float3 float2 = new float3(triangle2.a.y, triangle2.b.y, triangle2.c.y);
		float3 float3 = @float - @float.yzx;
		float3 float4 = float2 - float2.yzx;
		float num = math.dot(@float, float2.yzx - float2.zxy) * 0.5f;
		float num2 = math.csum(math.sqrt(float3 * float3 + float4 * float4));
		return num / (num2 * num2);
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
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_UpdatedAreasQuery = GetEntityQuery(ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Updated>(), ComponentType.ReadOnly<Node>(), ComponentType.ReadWrite<Triangle>());
		m_AllAreasQuery = GetEntityQuery(ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Node>(), ComponentType.ReadWrite<Triangle>());
		m_CreatedBuildingsQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Owner>(), ComponentType.Exclude<Temp>());
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
		EntityQuery entityQuery = (GetLoaded() ? m_AllAreasQuery : m_UpdatedAreasQuery);
		if (!entityQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			NativeList<Entity> list = entityQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
			JobHandle outJobHandle2;
			NativeList<Entity> buildings = m_CreatedBuildingsQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle2);
			JobHandle deps;
			JobHandle jobHandle = new TriangulateAreasJob
			{
				m_Entities = list.AsDeferredJobArray(),
				m_Buildings = buildings,
				m_SpaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Space_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTerrainAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TerrainAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(waitForPending: true),
				m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
				m_AreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Area_RW_ComponentLookup, ref base.CheckedStateRef),
				m_GeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RW_BufferLookup, ref base.CheckedStateRef),
				m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RW_BufferLookup, ref base.CheckedStateRef)
			}.Schedule(list, 1, JobUtils.CombineDependencies(base.Dependency, outJobHandle2, outJobHandle, deps));
			list.Dispose(jobHandle);
			buildings.Dispose(jobHandle);
			m_TerrainSystem.AddCPUHeightReader(jobHandle);
			m_WaterSystem.AddSurfaceReader(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```

- `private static Snip(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.GeometrySystem+Index index0, Game.Areas.GeometrySystem+Index index1, Game.Areas.GeometrySystem+Index index2, System.Int32 nodeCount, System.Int32 totalDepth, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, Unity.Collections.NativeArray<Game.Areas.GeometrySystem+Index> indexBuffer) : System.Boolean`  

```csharp
private static bool Snip(NativeArray<float3> nodes, Index index0, Index index1, Index index2, int nodeCount, int totalDepth, NativeArray<Bounds2> edgeBounds, NativeArray<Index> indexBuffer)
	{
		Triangle2 triangle = new Triangle2(nodes[index0.m_NodeIndex].xz, nodes[index1.m_NodeIndex].xz, nodes[index2.m_NodeIndex].xz);
		float2 @float = (triangle.b - triangle.a) * (triangle.c - triangle.a).yx;
		if (@float.x - @float.y < float.Epsilon)
		{
			return false;
		}
		if (edgeBounds.IsCreated)
		{
			Bounds2 bounds = MathUtils.Bounds(triangle);
			int num = 0;
			int num2 = 1;
			int num3 = 0;
			while (num2 > 0)
			{
				if (MathUtils.Intersect(edgeBounds[num + num3], bounds))
				{
					if (num2 != totalDepth)
					{
						num3 <<= 1;
						num += 1 << num2++;
						continue;
					}
					int num4 = num3 * nodes.Length >> num2;
					int num5 = (num3 + 1) * nodes.Length >> num2;
					for (int i = num4; i < num5; i++)
					{
						if (i != index0.m_NodeIndex && i != index1.m_NodeIndex && i != index2.m_NodeIndex && MathUtils.Intersect(triangle, nodes[i].xz))
						{
							return false;
						}
					}
				}
				while ((num3 & 1) != 0)
				{
					num3 >>= 1;
					num -= 1 << --num2;
				}
				num3++;
			}
		}
		else
		{
			Index index3 = indexBuffer[index2.m_NextIndex];
			for (int j = 3; j < nodeCount; j++)
			{
				if (MathUtils.Intersect(triangle, nodes[index3.m_NodeIndex].xz))
				{
					return false;
				}
				index3 = indexBuffer[index3.m_NextIndex];
			}
		}
		return true;
	}
```

- `public TerrainHeightsReadyAfterLoading() : System.Void`  

```csharp
public void TerrainHeightsReadyAfterLoading()
	{
		m_Loaded = true;
	}
```

- `public static Triangulate<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, System.Int32 totalDepth, System.Boolean isCounterClockwise) : System.Void`  

```csharp
public static System.Void Triangulate<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, System.Int32 totalDepth, System.Boolean isCounterClockwise);
```

- `private static TurnEdgeIfNeeded<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, Unity.Mathematics.int2> edgeMap, Unity.Mathematics.int2 index1, Unity.Mathematics.int2 index2) : System.Boolean`  

```csharp
private static System.Boolean TurnEdgeIfNeeded<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, Unity.Mathematics.int2> edgeMap, Unity.Mathematics.int2 index1, Unity.Mathematics.int2 index2);
```


## Nested types

- `Game.Areas.GeometrySystem+TriangulateAreasJob`  
- `Game.Areas.GeometrySystem+Index`  
- `Game.Areas.GeometrySystem+TypeHandle`  

