# Game.CinemachineDollyCartLookExtension

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Cinemachine.CinemachineExtension`  

## Code

```csharp
public class CinemachineDollyCartLookExtension : Cinemachine.CinemachineExtension
{
    public Game.CinemachineDollyCartLookExtension+DollyLookAngleOverride[] m_Angles;

    public CinemachineDollyCartLookExtension();

    private UnityEngine.Quaternion GetAngleOffset(Cinemachine.CinemachinePathBase path, System.Int32 t);
    private System.Single GetBoundingIndices(System.Single pos, System.Boolean looped, System.Int32& indexA, System.Int32& indexB);
    public System.Single GetMaxPos(System.Boolean looped);
    protected virtual System.Void PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime);
    public virtual System.Single StandardizePos(System.Single pos, System.Boolean looped);
}
```


## Fields

- `public Game.CinemachineDollyCartLookExtension+DollyLookAngleOverride[] m_Angles`  

```csharp
public Game.CinemachineDollyCartLookExtension+DollyLookAngleOverride[] m_Angles;
```


## Constructors

- `public CinemachineDollyCartLookExtension()`  

```csharp
public CinemachineDollyCartLookExtension();
```


## Methods

- `private GetAngleOffset(Cinemachine.CinemachinePathBase path, System.Int32 t) : UnityEngine.Quaternion`  

```csharp
private Quaternion GetAngleOffset(CinemachinePathBase path, int t)
	{
		if (m_Angles[t].m_OverrideLookAngle)
		{
			Vector3 eulerAngles = path.EvaluateOrientation(t).eulerAngles;
			eulerAngles.z = 0f;
			return Quaternion.Euler(m_Angles[t].m_Angle - eulerAngles);
		}
		return Quaternion.Euler(0f, 0f, 0f);
	}
```

- `private GetBoundingIndices(System.Single pos, System.Boolean looped, System.Int32& indexA, System.Int32& indexB) : System.Single`  

```csharp
private float GetBoundingIndices(float pos, bool looped, out int indexA, out int indexB)
	{
		pos = StandardizePos(pos, looped);
		int num = m_Angles.Length;
		if (num < 2)
		{
			indexA = (indexB = 0);
		}
		else
		{
			indexA = Mathf.FloorToInt(pos);
			if (indexA >= num)
			{
				pos -= GetMaxPos(looped);
				indexA = 0;
			}
			indexB = indexA + 1;
			if (indexB == num)
			{
				if (looped)
				{
					indexB = 0;
				}
				else
				{
					indexB--;
					indexA--;
				}
			}
		}
		return pos;
	}
```

- `public GetMaxPos(System.Boolean looped) : System.Single`  

```csharp
public float GetMaxPos(bool looped)
	{
		int num = m_Angles.Length - 1;
		if (num < 1)
		{
			return 0f;
		}
		return looped ? (num + 1) : num;
	}
```

- `protected virtual PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime) : System.Void`  

```csharp
protected override void PostPipelineStageCallback(CinemachineVirtualCameraBase vcam, CinemachineCore.Stage stage, ref CameraState state, float deltaTime)
	{
		if (stage != CinemachineCore.Stage.Aim)
		{
			return;
		}
		CinemachineDollyCart component = GetComponent<CinemachineDollyCart>();
		if (m_Angles.Length != 0 && component.m_PositionUnits == CinemachinePathBase.PositionUnits.PathUnits)
		{
			CinemachinePathBase path = component.m_Path;
			int indexA;
			int indexB;
			float boundingIndices = GetBoundingIndices(component.m_Position, path.Looped, out indexA, out indexB);
			Quaternion quaternion;
			if (indexA == indexB)
			{
				quaternion = GetAngleOffset(path, indexA);
			}
			else
			{
				Quaternion angleOffset = GetAngleOffset(path, indexA);
				Quaternion angleOffset2 = GetAngleOffset(path, indexB);
				quaternion = Quaternion.Slerp(angleOffset, angleOffset2, boundingIndices - (float)indexA);
			}
			Vector3 eulerAngles = quaternion.eulerAngles;
			eulerAngles.z = 0f;
			Vector3 eulerAngles2 = component.m_Path.EvaluateOrientation(boundingIndices).eulerAngles;
			eulerAngles2.z = 0f;
			state.RawOrientation = Quaternion.Euler(eulerAngles2 + eulerAngles);
		}
	}
```

- `public virtual StandardizePos(System.Single pos, System.Boolean looped) : System.Single`  

```csharp
public virtual float StandardizePos(float pos, bool looped)
	{
		float maxPos = GetMaxPos(looped);
		if (looped && maxPos > 0f)
		{
			pos %= maxPos;
			if (pos < 0f)
			{
				pos += maxPos;
			}
			return pos;
		}
		return Mathf.Clamp(pos, 0f, maxPos);
	}
```


## Nested types

- `Game.CinemachineDollyCartLookExtension+DollyLookAngleOverride`  

