# Game.CinemachineDollyCartLookExtension

**Assembly:** Assembly-CSharp.dll  
**Namespace:** Game

**Type:** class

**Base:** Cinemachine.CinemachineExtension

**Summary:** A Cinemachine extension that allows per-path-position overrides of the look/aim angle for a CinemachineDollyCart. It stores an array of angle overrides (DollyLookAngleOverride) and, during the Aim pipeline stage, applies either a single override or a smoothly interpolated override between two neighboring entries to modify the camera's final orientation. The extension expects the dolly cart to use PathUnits for its position to match the array indexing semantics.
---

## Fields

- `public DollyLookAngleOverride[] m_Angles`  
Array of per-position angle override records. Each array index corresponds to a path "integer" position. The array length determines valid indices; when the path is looped, the indexing logic treats the positions cyclically (see GetMaxPos/StandardizePos/GetBoundingIndices).

- `public struct DollyLookAngleOverride`  
  The nested struct used by m_Angles:
  - `public bool m_OverrideLookAngle` — whether the angle override is active for this entry. If false, no offset is applied for that index.
  - `public Vector3 m_Angle` — the Euler angles (in degrees) to apply as the override when m_OverrideLookAngle is true.
  Use: an entry with m_OverrideLookAngle=false is treated as identity (no offset).

## Properties

- None.  
This component exposes no C# properties; it uses public fields and overrides from CinemachineExtension.

## Constructors

- `public CinemachineDollyCartLookExtension()`  
Default constructor (implicit if not defined). The component is intended to be used as a Unity component (MonoBehaviour-style) attached alongside a CinemachineDollyCart on a GameObject.

## Methods

- `public float GetMaxPos(bool looped)`  
Returns the maximum "position" value used for indexing/normalization based on m_Angles length. If m_Angles.Length < 2 returns 0. For non-looped paths the max position equals (m_Angles.Length - 1). For looped paths it returns (m_Angles.Length) so the last element wraps back to index 0. Use this value when normalizing or clamping positions.

- `public virtual float StandardizePos(float pos, bool looped)`  
Converts a raw position into the canonical range used by this extension:
  - If looped and maxPos > 0: performs modulo wrapping to [0, maxPos), also handles negative inputs.
  - If not looped: clamps pos into [0, maxPos].
Returns the adjusted position. This is used as the first step when mapping a dolly cart position to array indices.

- `private float GetBoundingIndices(float pos, bool looped, out int indexA, out int indexB)`  
Normalizes pos (via StandardizePos) and computes the integer indices indexA and indexB that bound pos for interpolation:
  - If the array has fewer than 2 entries, both indices are set to 0.
  - indexA = floor(pos). If indexA >= num and path is looped, indexA is wrapped to 0 and pos reduced accordingly.
  - indexB = indexA + 1. If indexB == num and not looped, indexB and indexA are decremented to pick the last valid segment.
Returns the (standardized) pos used for interpolation. This method encapsulates the boundary and wrapping rules used by the extension.

- `protected override void PostPipelineStageCallback(CinemachineVirtualCameraBase vcam, CinemachineCore.Stage stage, ref CameraState state, float deltaTime)`  
Runs during Cinemachine pipeline stages. This override:
  - Only runs its logic when stage == CinemachineCore.Stage.Aim (otherwise it returns immediately).
  - Gets the CinemachineDollyCart component on the same GameObject.
  - If m_Angles is not empty and the dolly cart uses PathUnits, it:
    - Determines the two bounding angle indices (indexA/indexB) and an interpolation position.
    - Gets each index's angle offset via GetAngleOffset. If indices are different, Slerp interpolates between the two Quaternions.
    - Clears the z-component (roll) of both the computed offset and the path's evaluated orientation to avoid roll application.
    - Adds the angle offset to the path orientation and sets state.RawOrientation to the resulting orientation.
Notes:
  - This method modifies the camera's raw orientation directly; it replaces the aim orientation, so any other Aim-stage extensions should be considered when chaining effects.
  - It only supports dolly cart positions expressed in PathUnits. If the cart uses WorldUnits or other units, the extension does nothing.

- `private Quaternion GetAngleOffset(CinemachinePathBase path, int t)`  
Returns the rotation offset that should be applied at integer index t:
  - If m_Angles[t].m_OverrideLookAngle is true: computes path.EvaluateOrientation(t), zeroes its z (roll), then returns Quaternion.Euler(m_Angles[t].m_Angle - pathOrientationEuler) — i.e., the delta between desired override Euler angles and the path's base orientation at t.
  - If override flag is false: returns identity (Quaternion.Euler(0,0,0)), meaning no offset.
Edge cases:
  - Caller must ensure index t is within bounds of m_Angles.

## Example (core method)

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

Additional notes:
- Ensure the dolly cart component and path are present and properly configured (PathUnits) for the extension to take effect.
- When authoring m_Angles entries, consider how the array length maps to path positions and whether the path is looped to avoid unexpected wrap-around behavior.