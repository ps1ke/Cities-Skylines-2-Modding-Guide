# Game.Rendering.NotificationIconRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationIconRenderSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.NotificationIconBufferSystem m_BufferSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private UnityEngine.Mesh m_Mesh;
    private UnityEngine.Material m_Material;
    private UnityEngine.ComputeBuffer m_ArgsBuffer;
    private UnityEngine.ComputeBuffer m_InstanceBuffer;
    private UnityEngine.Texture2DArray m_TextureArray;
    private System.UInt32[] m_ArgsArray;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private System.Int32 m_InstanceBufferID;
    private System.Boolean m_UpdateBuffer;
    private Game.Rendering.NotificationIconRenderSystem+TypeHandle __TypeHandle;

    public NotificationIconRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void DisplayDataUpdated();
    private UnityEngine.ComputeBuffer GetArgsBuffer();
    private UnityEngine.ComputeBuffer GetInstanceBuffer(System.Int32 count);
    private UnityEngine.Material GetMaterial();
    private UnityEngine.Mesh GetMesh();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.NotificationIconBufferSystem m_BufferSystem`  

```csharp
private Game.Rendering.NotificationIconBufferSystem m_BufferSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private UnityEngine.Mesh m_Mesh`  

```csharp
private UnityEngine.Mesh m_Mesh;
```

- `private UnityEngine.Material m_Material`  

```csharp
private UnityEngine.Material m_Material;
```

- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_ArgsBuffer;
```

- `private UnityEngine.ComputeBuffer m_InstanceBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_InstanceBuffer;
```

- `private UnityEngine.Texture2DArray m_TextureArray`  

```csharp
private UnityEngine.Texture2DArray m_TextureArray;
```

- `private System.UInt32[] m_ArgsArray`  

```csharp
private System.UInt32[] m_ArgsArray;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private System.Int32 m_InstanceBufferID`  

```csharp
private System.Int32 m_InstanceBufferID;
```

- `private System.Boolean m_UpdateBuffer`  

```csharp
private System.Boolean m_UpdateBuffer;
```

- `private Game.Rendering.NotificationIconRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.NotificationIconRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationIconRenderSystem()`  

```csharp
[Preserve]
	public NotificationIconRenderSystem()
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

- `public DisplayDataUpdated() : System.Void`  

```csharp
public void DisplayDataUpdated()
	{
		if (m_Material != null)
		{
			Object.Destroy(m_Material);
			m_Material = null;
		}
		if (m_TextureArray != null)
		{
			Object.Destroy(m_TextureArray);
			m_TextureArray = null;
		}
	}
```

- `private GetArgsBuffer() : UnityEngine.ComputeBuffer`  

```csharp
private ComputeBuffer GetArgsBuffer()
	{
		if (m_ArgsBuffer == null)
		{
			m_ArgsArray = new uint[5];
			m_ArgsBuffer = new ComputeBuffer(1, m_ArgsArray.Length * 4, ComputeBufferType.DrawIndirect);
			m_ArgsBuffer.name = "Notification args buffer";
		}
		return m_ArgsBuffer;
	}
```

- `private GetInstanceBuffer(System.Int32 count) : UnityEngine.ComputeBuffer`  

```csharp
private unsafe ComputeBuffer GetInstanceBuffer(int count)
	{
		if (m_InstanceBuffer != null && m_InstanceBuffer.count < count)
		{
			count = math.max(m_InstanceBuffer.count * 2, count);
			m_InstanceBuffer.Release();
			m_InstanceBuffer = null;
		}
		if (m_InstanceBuffer == null)
		{
			m_InstanceBuffer = new ComputeBuffer(math.max(64, count), sizeof(NotificationIconBufferSystem.InstanceData));
			m_InstanceBuffer.name = "Notification instance buffer";
		}
		return m_InstanceBuffer;
	}
```

- `private GetMaterial() : UnityEngine.Material`  

```csharp
private Material GetMaterial()
	{
		if (m_Material == null)
		{
			Entity singletonEntity = m_ConfigurationQuery.GetSingletonEntity();
			IconConfigurationPrefab prefab = m_PrefabSystem.GetPrefab<IconConfigurationPrefab>(singletonEntity);
			m_Material = new Material(prefab.m_Material);
			m_Material.name = "Notification icons";
			NativeArray<ArchetypeChunk> nativeArray = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
			ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NotificationIconDisplayData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NotificationIconDisplayData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			try
			{
				int num = 1;
				int2 x = new int2(prefab.m_MissingIcon.width, prefab.m_MissingIcon.height);
				TextureFormat format = prefab.m_MissingIcon.format;
				for (int i = 0; i < nativeArray.Length; i++)
				{
					ArchetypeChunk archetypeChunk = nativeArray[i];
					EnabledMask enabledMask = archetypeChunk.GetEnabledMask(ref typeHandle);
					NativeArray<PrefabData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle);
					NativeArray<NotificationIconDisplayData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
					for (int j = 0; j < nativeArray2.Length; j++)
					{
						if (enabledMask[j])
						{
							PrefabData prefabData = nativeArray2[j];
							NotificationIconPrefab prefab2 = m_PrefabSystem.GetPrefab<NotificationIconPrefab>(prefabData);
							num = math.max(num, nativeArray3[j].m_IconIndex + 1);
							x = math.max(x, new int2(prefab2.m_Icon.width, prefab2.m_Icon.height));
							format = prefab2.m_Icon.format;
						}
					}
				}
				m_TextureArray = new Texture2DArray(x.x, x.y, num, format, mipChain: true)
				{
					name = "NotificationIcons"
				};
				Graphics.CopyTexture(prefab.m_MissingIcon, 0, m_TextureArray, 0);
				for (int k = 0; k < nativeArray.Length; k++)
				{
					ArchetypeChunk archetypeChunk2 = nativeArray[k];
					EnabledMask enabledMask2 = archetypeChunk2.GetEnabledMask(ref typeHandle);
					NativeArray<PrefabData> nativeArray4 = archetypeChunk2.GetNativeArray(ref typeHandle);
					NativeArray<NotificationIconDisplayData> nativeArray5 = archetypeChunk2.GetNativeArray(ref typeHandle2);
					for (int l = 0; l < nativeArray4.Length; l++)
					{
						if (enabledMask2[l])
						{
							PrefabData prefabData2 = nativeArray4[l];
							NotificationIconPrefab prefab3 = m_PrefabSystem.GetPrefab<NotificationIconPrefab>(prefabData2);
							NotificationIconDisplayData notificationIconDisplayData = nativeArray5[l];
							Graphics.CopyTexture(prefab3.m_Icon, 0, m_TextureArray, notificationIconDisplayData.m_IconIndex);
						}
					}
				}
				m_Material.mainTexture = m_TextureArray;
			}
			finally
			{
				nativeArray.Dispose();
			}
		}
		return m_Material;
	}
```

- `private GetMesh() : UnityEngine.Mesh`  

```csharp
private Mesh GetMesh()
	{
		if (m_Mesh == null)
		{
			m_Mesh = new Mesh();
			m_Mesh.name = "Notification icon";
			m_Mesh.vertices = new Vector3[4]
			{
				new Vector3(-1f, -1f, 0f),
				new Vector3(-1f, 1f, 0f),
				new Vector3(1f, 1f, 0f),
				new Vector3(1f, -1f, 0f)
			};
			m_Mesh.uv = new Vector2[4]
			{
				new Vector2(0f, 0f),
				new Vector2(0f, 1f),
				new Vector2(1f, 1f),
				new Vector2(1f, 0f)
			};
			m_Mesh.triangles = new int[6] { 0, 1, 2, 2, 3, 0 };
		}
		return m_Mesh;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_BufferSystem = base.World.GetOrCreateSystemManaged<NotificationIconBufferSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<IconConfigurationData>());
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<NotificationIconData>(), ComponentType.ReadOnly<PrefabData>());
		m_InstanceBufferID = Shader.PropertyToID("instanceBuffer");
		RequireForUpdate(m_ConfigurationQuery);
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
		if (m_Material != null)
		{
			Object.Destroy(m_Material);
		}
		if (m_ArgsBuffer != null)
		{
			m_ArgsBuffer.Release();
		}
		if (m_InstanceBuffer != null)
		{
			m_InstanceBuffer.Release();
		}
		if (m_TextureArray != null)
		{
			Object.Destroy(m_TextureArray);
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_UpdateBuffer = true;
	}
```

- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

```csharp
private void Render(ScriptableRenderContext context, List<Camera> cameras)
	{
		try
		{
			if (m_RenderingSystem.hideOverlay)
			{
				return;
			}
			NotificationIconBufferSystem.IconData iconData = m_BufferSystem.GetIconData();
			if (!iconData.m_InstanceData.IsCreated)
			{
				return;
			}
			int length = iconData.m_InstanceData.Length;
			if (length == 0)
			{
				return;
			}
			Bounds bounds = RenderingUtils.ToBounds(iconData.m_IconBounds.value);
			Mesh mesh = GetMesh();
			Material material = GetMaterial();
			ComputeBuffer argsBuffer = GetArgsBuffer();
			m_ArgsArray[0] = mesh.GetIndexCount(0);
			m_ArgsArray[1] = (uint)length;
			m_ArgsArray[2] = mesh.GetIndexStart(0);
			m_ArgsArray[3] = mesh.GetBaseVertex(0);
			m_ArgsArray[4] = 0u;
			argsBuffer.SetData(m_ArgsArray);
			if (m_UpdateBuffer)
			{
				m_UpdateBuffer = false;
				ComputeBuffer instanceBuffer = GetInstanceBuffer(length);
				instanceBuffer.SetData(iconData.m_InstanceData, 0, 0, length);
				material.SetBuffer(m_InstanceBufferID, instanceBuffer);
			}
			foreach (Camera camera in cameras)
			{
				if (camera.cameraType == CameraType.Game || camera.cameraType == CameraType.SceneView)
				{
					Graphics.DrawMeshInstancedIndirect(mesh, 0, material, bounds, argsBuffer, 0, null, ShadowCastingMode.Off, receiveShadows: false, 0, camera);
				}
			}
		}
		finally
		{
		}
	}
```


## Nested types

- `Game.Rendering.NotificationIconRenderSystem+TypeHandle`  

