# Game.Debug.CameraDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public static class CameraDebugUI
{
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildCameraDebugUI(Unity.Entities.World world);
}
```


## Methods

- `private static BuildCameraDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildCameraDebugUI(World world)
	{
		CameraUpdateSystem cameraUpdateSystem = world.GetExistingSystemManaged<CameraUpdateSystem>();
		float minClip = -50f;
		float maxClip = 1000f;
		DebugUI.Container container = new DebugUI.Container
		{
			displayName = "Game Cameras"
		};
		Camera[] allCameras = Camera.allCameras;
		for (int i = 0; i < allCameras.Length; i++)
		{
			Camera camera = allCameras[i];
			if (camera.cameraType == CameraType.Game)
			{
				container.children.Add(new DebugUI.Foldout
				{
					displayName = $"#{i} {camera.name}",
					children = 
					{
						(DebugUI.Widget)new DebugUI.Value
						{
							displayName = "Is Main?",
							getter = () => (camera == Camera.main).ToString()
						},
						(DebugUI.Widget)new DebugUI.Value
						{
							displayName = "Is ActiveViewer?",
							getter = () => (camera == cameraUpdateSystem.activeViewer?.camera).ToString()
						},
						(DebugUI.Widget)new DebugUI.Value
						{
							displayName = "World Position",
							getter = () => camera?.transform.position.ToString()
						},
						(DebugUI.Widget)new DebugUI.Value
						{
							displayName = "Focus distance",
							getter = () => camera?.transform.position.ToString()
						}
					}
				});
			}
		}
		DebugUI.Foldout item = new DebugUI.Foldout
		{
			displayName = "Active Viewer",
			children = 
			{
				(DebugUI.Widget)new DebugUI.Value
				{
					displayName = "World Position",
					getter = () => $"({cameraUpdateSystem.activeViewer?.position.x:F2}, {cameraUpdateSystem.activeViewer?.position.y:F2}, {cameraUpdateSystem.activeViewer?.position.z:F2})"
				},
				(DebugUI.Widget)new DebugUI.Value
				{
					displayName = "Visibility distance",
					getter = () => cameraUpdateSystem.activeViewer?.visibilityDistance.ToString("F1")
				},
				(DebugUI.Widget)new DebugUI.Value
				{
					displayName = "Focus distance",
					getter = () => cameraUpdateSystem.activeViewer?.viewerDistances.focus.ToString("F1")
				},
				(DebugUI.Widget)new DebugUI.BoolField
				{
					displayName = "Shadows Adjust Start Dist",
					getter = () => cameraUpdateSystem.activeViewer?.shadowsAdjustStartDistance ?? false,
					setter = delegate(bool value)
					{
						if (cameraUpdateSystem.activeViewer != null)
						{
							cameraUpdateSystem.activeViewer.shadowsAdjustStartDistance = value;
						}
					}
				},
				(DebugUI.Widget)new DebugUI.FloatField
				{
					displayName = "Push culling near mult",
					getter = () => cameraUpdateSystem.activeViewer?.pushCullingNearPlaneMultiplier ?? 0f,
					setter = delegate(float value)
					{
						if (cameraUpdateSystem.activeViewer != null)
						{
							cameraUpdateSystem.activeViewer.pushCullingNearPlaneMultiplier = value;
						}
					},
					min = () => 0.1f,
					max = () => 1f,
					incStep = 0.05f
				},
				(DebugUI.Widget)new DebugUI.FloatField
				{
					displayName = "Push culling near value",
					getter = () => cameraUpdateSystem.activeViewer?.pushCullingNearPlaneValue ?? 0f,
					setter = delegate(float value)
					{
						if (cameraUpdateSystem.activeViewer != null)
						{
							cameraUpdateSystem.activeViewer.pushCullingNearPlaneValue = value;
						}
					},
					min = () => 0f,
					max = () => 1000f,
					incStep = 10f
				},
				(DebugUI.Widget)new DebugUI.BoolField
				{
					displayName = "Shadows Adjust Far Dist",
					getter = () => cameraUpdateSystem.activeViewer?.shadowsAdjustFarDistance ?? false,
					setter = delegate(bool value)
					{
						if (cameraUpdateSystem.activeViewer != null)
						{
							cameraUpdateSystem.activeViewer.shadowsAdjustFarDistance = value;
						}
					}
				},
				(DebugUI.Widget)new DebugUI.Value
				{
					displayName = "Closest surface",
					getter = () => cameraUpdateSystem.activeViewer?.viewerDistances.closestSurface.ToString("F1")
				},
				(DebugUI.Widget)new DebugUI.Value
				{
					displayName = "Farthest surface",
					getter = () => cameraUpdateSystem.activeViewer?.viewerDistances.farthestSurface.ToString("F1")
				},
				(DebugUI.Widget)new DebugUI.Value
				{
					displayName = "Average surface",
					getter = () => cameraUpdateSystem.activeViewer?.viewerDistances.averageSurface.ToString("F1")
				},
				(DebugUI.Widget)new DebugUI.Value
				{
					displayName = "Ground distance",
					getter = () => cameraUpdateSystem.activeViewer?.viewerDistances.ground.ToString("F1")
				},
				(DebugUI.Widget)new DebugUI.Value
				{
					displayName = "Sea level view dist",
					getter = () => cameraUpdateSystem.activeViewer?.viewerDistances.maxDistanceToSeaLevel.ToString("F1")
				}
			}
		};
		container.children.Add(item);
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Cinemachine"
		};
		for (int num = 0; num < CinemachineCore.Instance.BrainCount; num++)
		{
			CinemachineCore.Instance.GetActiveBrain(num);
			for (int num2 = 0; num2 < CinemachineCore.Instance.VirtualCameraCount; num2++)
			{
				ICinemachineCamera vcam = CinemachineCore.Instance.GetVirtualCamera(num2);
				foldout.children.Add(new DebugUI.Value
				{
					displayName = vcam.Name,
					getter = delegate
					{
						for (int j = 0; j < CinemachineCore.Instance.BrainCount; j++)
						{
							if (CinemachineCore.Instance.GetActiveBrain(j).ActiveVirtualCamera == vcam)
							{
								return "Active";
							}
						}
						return "Inactive";
					}
				});
			}
		}
		container.children.Add(foldout);
		CameraController cameraController;
		return new List<DebugUI.Widget>
		{
			container,
			new DebugUI.BoolField
			{
				displayName = "Edge-scrolling",
				getter = () => CameraController.TryGet(out cameraController) && cameraController.edgeScrolling,
				setter = delegate(bool value)
				{
					if (CameraController.TryGet(out cameraController))
					{
						cameraController.edgeScrolling = value;
					}
				}
			},
			new DebugUI.FloatField
			{
				displayName = "Clip offset",
				min = () => minClip,
				max = () => maxClip,
				incStep = 1f,
				incStepMult = 1f,
				decimals = 0,
				getter = () => CameraController.TryGet(out cameraController) ? ((cameraController.clipDistance == float.MaxValue) ? maxClip : cameraController.clipDistance) : 0f,
				setter = delegate(float value)
				{
					if (CameraController.TryGet(out cameraController))
					{
						cameraController.clipDistance = math.select(value, float.MaxValue, value == maxClip);
					}
				}
			}
		};
	}
```


## Nested types

- `Game.Debug.CameraDebugUI+<>c`  
- `Game.Debug.CameraDebugUI+<>c__DisplayClass0_0`  
- `Game.Debug.CameraDebugUI+<>c__DisplayClass0_1`  
- `Game.Debug.CameraDebugUI+<>c__DisplayClass0_2`  

