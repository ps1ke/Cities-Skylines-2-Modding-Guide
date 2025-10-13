# Game.Rendering.AggregateRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class AggregateRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.AggregateMeshSystem m_AggregateMeshSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Tools.ToolSystem m_ToolSystem;

    public AggregateRenderSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
}
```


## Fields

- `private Game.Rendering.AggregateMeshSystem m_AggregateMeshSystem`  

```csharp
private Game.Rendering.AggregateMeshSystem m_AggregateMeshSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```


## Constructors

- `public AggregateRenderSystem()`  

```csharp
[Preserve]
	public AggregateRenderSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_AggregateMeshSystem = base.World.GetOrCreateSystemManaged<AggregateMeshSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		RenderPipelineManager.beginContextRendering += Render;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		RenderPipelineManager.beginContextRendering -= Render;
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
			if (m_RenderingSystem.hideOverlay)
			{
				return;
			}
			if (m_ToolSystem.activeTool != null && m_ToolSystem.activeTool.requireNetArrows)
			{
				int arrowMaterialCount = m_AggregateMeshSystem.GetArrowMaterialCount();
				for (int i = 0; i < arrowMaterialCount; i++)
				{
					if (!m_AggregateMeshSystem.GetArrowMesh(i, out var mesh, out var subMeshCount))
					{
						continue;
					}
					for (int j = 0; j < subMeshCount; j++)
					{
						if (!m_AggregateMeshSystem.GetArrowMaterial(i, j, out var material))
						{
							continue;
						}
						foreach (Camera camera in cameras)
						{
							if (camera.cameraType == CameraType.Game || camera.cameraType == CameraType.SceneView)
							{
								Graphics.DrawMesh(mesh, Matrix4x4.identity, material, 0, camera, j, null, castShadows: false, receiveShadows: false);
							}
						}
					}
				}
				return;
			}
			int nameMaterialCount = m_AggregateMeshSystem.GetNameMaterialCount();
			for (int k = 0; k < nameMaterialCount; k++)
			{
				if (!m_AggregateMeshSystem.GetNameMesh(k, out var mesh2, out var subMeshCount2))
				{
					continue;
				}
				for (int l = 0; l < subMeshCount2; l++)
				{
					if (!m_AggregateMeshSystem.GetNameMaterial(k, l, out var material2))
					{
						continue;
					}
					foreach (Camera camera2 in cameras)
					{
						if (camera2.cameraType == CameraType.Game || camera2.cameraType == CameraType.SceneView)
						{
							Graphics.DrawMesh(mesh2, Matrix4x4.identity, material2, 0, camera2, l, null, castShadows: false, receiveShadows: false);
						}
					}
				}
			}
		}
		finally
		{
		}
	}
```


