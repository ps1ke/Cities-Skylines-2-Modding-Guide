# Game.Rendering.RouteRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteRenderSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.RouteBufferSystem m_RouteBufferSystem;
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Unity.Entities.EntityQuery m_LivePathQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private UnityEngine.Mesh m_Mesh;
    private UnityEngine.ComputeBuffer m_ArgsBuffer;
    private System.Collections.Generic.List<System.UInt32> m_ArgsArray;
    private System.Int32 m_RouteSegmentBuffer;
    private System.Int32 m_RouteColor;
    private System.Int32 m_RouteSize;
    private Game.Rendering.RouteRenderSystem+TypeHandle __TypeHandle;

    public RouteRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void EnsureMesh();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
    private System.Boolean ShouldRenderRoutes();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.RouteBufferSystem m_RouteBufferSystem`  

```csharp
private Game.Rendering.RouteBufferSystem m_RouteBufferSystem;
```

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Unity.Entities.EntityQuery m_LivePathQuery`  

```csharp
private Unity.Entities.EntityQuery m_LivePathQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private UnityEngine.Mesh m_Mesh`  

```csharp
private UnityEngine.Mesh m_Mesh;
```

- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_ArgsBuffer;
```

- `private System.Collections.Generic.List<System.UInt32> m_ArgsArray`  

```csharp
private System.Collections.Generic.List<System.UInt32> m_ArgsArray;
```

- `private System.Int32 m_RouteSegmentBuffer`  

```csharp
private System.Int32 m_RouteSegmentBuffer;
```

- `private System.Int32 m_RouteColor`  

```csharp
private System.Int32 m_RouteColor;
```

- `private System.Int32 m_RouteSize`  

```csharp
private System.Int32 m_RouteSize;
```

- `private Game.Rendering.RouteRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.RouteRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteRenderSystem()`  

```csharp
[Preserve]
	public RouteRenderSystem()
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

- `private EnsureMesh() : System.Void`  

```csharp
private void EnsureMesh()
	{
		if (!(m_Mesh == null))
		{
			return;
		}
		Vector3[] array = new Vector3[68];
		Vector2[] array2 = new Vector2[array.Length];
		int[] array3 = new int[192];
		int num = 0;
		int num2 = 0;
		for (int i = 0; i <= 16; i++)
		{
			float num3 = (float)i / 16f;
			array[num] = new Vector3(-1f, 0f, num3);
			array2[num] = new Vector2(0f, num3);
			num++;
			array[num] = new Vector3(1f, 0f, num3);
			array2[num] = new Vector2(0f, num3);
			num++;
			if (i != 0)
			{
				array3[num2++] = num - 4;
				array3[num2++] = num - 3;
				array3[num2++] = num - 2;
				array3[num2++] = num - 2;
				array3[num2++] = num - 3;
				array3[num2++] = num - 1;
			}
		}
		for (int j = 0; j <= 16; j++)
		{
			float num4 = (float)j / 16f;
			array[num] = new Vector3(0f, -1f, num4);
			array2[num] = new Vector2(1f, num4);
			num++;
			array[num] = new Vector3(0f, 1f, num4);
			array2[num] = new Vector2(1f, num4);
			num++;
			if (j != 0)
			{
				array3[num2++] = num - 4;
				array3[num2++] = num - 3;
				array3[num2++] = num - 2;
				array3[num2++] = num - 2;
				array3[num2++] = num - 3;
				array3[num2++] = num - 1;
			}
		}
		m_Mesh = new Mesh();
		m_Mesh.name = "Route segment";
		m_Mesh.vertices = array;
		m_Mesh.uv = array2;
		m_Mesh.triangles = array3;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_RouteBufferSystem = base.World.GetOrCreateSystemManaged<RouteBufferSystem>();
		m_RouteQuery = GetEntityQuery(ComponentType.ReadOnly<Route>(), ComponentType.ReadOnly<RouteWaypoint>(), ComponentType.ReadOnly<RouteSegment>(), ComponentType.Exclude<HiddenRoute>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Hidden>());
		m_LivePathQuery = GetEntityQuery(ComponentType.ReadOnly<LivePath>(), ComponentType.ReadOnly<RouteWaypoint>(), ComponentType.ReadOnly<RouteSegment>(), ComponentType.Exclude<HiddenRoute>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Hidden>());
		m_InfomodeQuery = GetEntityQuery(ComponentType.ReadOnly<InfomodeActive>(), ComponentType.ReadOnly<InfoviewRouteData>());
		m_RouteSegmentBuffer = Shader.PropertyToID("colossal_RouteSegmentBuffer");
		m_RouteColor = Shader.PropertyToID("colossal_RouteColor");
		m_RouteSize = Shader.PropertyToID("colossal_RouteSize");
		RenderPipelineManager.beginContextRendering += Render;
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
		RenderPipelineManager.beginContextRendering -= Render;
		if (m_Mesh != null)
		{
			Object.Destroy(m_Mesh);
		}
		if (m_ArgsBuffer != null)
		{
			m_ArgsBuffer.Release();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
	}
```

- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

```csharp
private void Render(ScriptableRenderContext context, List<Camera> cameras)
	{
		try
		{
			EntityQuery entityQuery = (ShouldRenderRoutes() ? m_RouteQuery : m_LivePathQuery);
			if (entityQuery.IsEmptyIgnoreFilter)
			{
				return;
			}
			NativeArray<ArchetypeChunk> nativeArray = entityQuery.ToArchetypeChunkArray(Allocator.TempJob);
			try
			{
				if (nativeArray.Length == 0)
				{
					return;
				}
				EnsureMesh();
				if (m_ArgsArray == null)
				{
					m_ArgsArray = new List<uint>();
				}
				m_ArgsArray.Clear();
				uint indexCount = m_Mesh.GetIndexCount(0);
				uint indexStart = m_Mesh.GetIndexStart(0);
				uint baseVertex = m_Mesh.GetBaseVertex(0);
				CompleteDependency();
				EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
				ComponentTypeHandle<RouteBufferIndex> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_RouteBufferIndex_RO_ComponentTypeHandle, ref base.CheckedStateRef);
				ComponentTypeHandle<Game.Routes.Color> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Color_RO_ComponentTypeHandle, ref base.CheckedStateRef);
				ComponentTypeHandle<Highlighted> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Highlighted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
				ComponentTypeHandle<Temp> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
				int num = 0;
				for (int i = 0; i < nativeArray.Length; i++)
				{
					num += nativeArray[i].Count * 5;
				}
				if (m_ArgsBuffer != null && m_ArgsBuffer.count < num)
				{
					m_ArgsBuffer.Release();
					m_ArgsBuffer = null;
				}
				if (m_ArgsBuffer == null)
				{
					m_ArgsBuffer = new ComputeBuffer(num, 4, ComputeBufferType.DrawIndirect);
					m_ArgsBuffer.name = "Route args buffer";
				}
				Entity selected = m_ToolSystem.selected;
				for (int j = 0; j < nativeArray.Length; j++)
				{
					ArchetypeChunk archetypeChunk = nativeArray[j];
					NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
					NativeArray<RouteBufferIndex> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
					NativeArray<Game.Routes.Color> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
					NativeArray<Temp> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle4);
					bool flag = archetypeChunk.Has(ref typeHandle3);
					for (int k = 0; k < nativeArray3.Length; k++)
					{
						RouteBufferIndex routeBufferIndex = nativeArray3[k];
						m_RouteBufferSystem.GetBuffer(routeBufferIndex.m_Index, out var material, out var segmentBuffer, out var originalRenderQueue, out var bounds, out var size);
						if (material == null || segmentBuffer == null)
						{
							continue;
						}
						int count = m_ArgsArray.Count;
						m_ArgsArray.Add(indexCount);
						m_ArgsArray.Add((uint)segmentBuffer.count);
						m_ArgsArray.Add(indexStart);
						m_ArgsArray.Add(baseVertex);
						m_ArgsArray.Add(0u);
						Game.Routes.Color color = nativeArray4[k];
						if (nativeArray2[k] == selected || flag || (nativeArray5.Length != 0 && (nativeArray5[k].m_Flags & (TempFlags.Create | TempFlags.Delete | TempFlags.Select | TempFlags.Modify)) != 0))
						{
							color.m_Color.a = byte.MaxValue;
							size.x *= 1.3333334f;
							material.renderQueue = originalRenderQueue + 1;
						}
						else
						{
							color.m_Color.a = 128;
							material.renderQueue = originalRenderQueue;
						}
						material.SetBuffer(m_RouteSegmentBuffer, segmentBuffer);
						material.SetColor(m_RouteColor, color.m_Color);
						material.SetVector(m_RouteSize, size);
						bounds.Expand(size.x);
						foreach (Camera camera in cameras)
						{
							if (camera.cameraType == CameraType.Game || camera.cameraType == CameraType.SceneView)
							{
								Graphics.DrawMeshInstancedIndirect(m_Mesh, 0, material, bounds, m_ArgsBuffer, count * 4, null, ShadowCastingMode.Off, receiveShadows: false, 0, camera);
							}
						}
					}
				}
			}
			finally
			{
				nativeArray.Dispose();
			}
			if (m_ArgsArray.Count > 0)
			{
				m_ArgsBuffer.SetData(m_ArgsArray, 0, 0, m_ArgsArray.Count);
			}
		}
		finally
		{
		}
	}
```

- `private ShouldRenderRoutes() : System.Boolean`  

```csharp
private bool ShouldRenderRoutes()
	{
		if ((m_ToolSystem.activeTool == null || m_ToolSystem.activeTool.requireRoutes == RouteType.None) && m_InfomodeQuery.IsEmptyIgnoreFilter)
		{
			return false;
		}
		return true;
	}
```


## Nested types

- `Game.Rendering.RouteRenderSystem+TypeHandle`  

