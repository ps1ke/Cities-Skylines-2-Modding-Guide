# Game.CinemachineGameAxisProvider

**Assembly:** Assembly-CSharp  
**Namespace:** Game

**Type:** class

**Base:** UnityEngine.MonoBehaviour, Cinemachine.AxisState.IInputAxisProvider

**Summary:** Bridges the game's input system to Cinemachine by implementing Cinemachine.AxisState.IInputAxisProvider. It reads the game's "Camera/Rotate" (Vector2) and "Camera/Zoom" (float) actions (via InputManager) and supplies those values as axes for Cinemachine virtual cameras. Intended for use where Cinemachine expects an input-axis provider (e.g., FreeLook rigs or other Cinemachine components that query axis values).
---

## Fields

- `private ProxyAction m_RotateAction`  
Holds the ProxyAction for the "Camera/Rotate" input. Expected to provide a Vector2 (x = horizontal rotation, y = vertical rotation). Populated in Awake using InputManager.instance.FindAction.

- `private ProxyAction m_ZoomAction`  
Holds the ProxyAction for the "Camera/Zoom" input. Expected to provide a float zoom value. Populated in Awake using InputManager.instance.FindAction.

## Properties

- `None`  
This class exposes no public properties. It implements input provisioning via the GetAxisValue method required by Cinemachine.AxisState.IInputAxisProvider.

## Constructors

- `public CinemachineGameAxisProvider()`  
Default MonoBehaviour constructor. No explicit constructor logic is defined in the source; initialization is performed in Awake.

## Methods

- `private void Awake()`  
Initializes the internal ProxyAction references by fetching actions from the game's InputManager. Called by Unity when the component is first instantiated/enabled.

```csharp
private void Awake()
{
	m_RotateAction = InputManager.instance.FindAction("Camera", "Rotate");
	m_ZoomAction = InputManager.instance.FindAction("Camera", "Zoom");
}
```

- `public float GetAxisValue(int axis)`  
Implements Cinemachine.AxisState.IInputAxisProvider.GetAxisValue. Returns axis values mapped as:
  - 0: horizontal rotation (m_RotateAction Vector2.x)
  - 1: vertical rotation (m_RotateAction Vector2.y)
  - 2: zoom (m_ZoomAction float)
  - default: 0f

Uses ReadRawValue<T>(disableAll: false) to read the underlying input value without disabling other bindings.

```csharp
public float GetAxisValue(int axis)
{
	return axis switch
	{
		0 => m_RotateAction.ReadRawValue<Vector2>(disableAll: false).x, 
		1 => m_RotateAction.ReadRawValue<Vector2>(disableAll: false).y, 
		2 => m_ZoomAction.ReadRawValue<float>(disableAll: false), 
		_ => 0f, 
	};
}
```

Additional notes:
- The class depends on Game.Input.InputManager and the ProxyAction abstraction; ensure those systems are present and that the "Camera/Rotate" and "Camera/Zoom" actions are defined in the input configuration.
- If Cinemachine queries axes frequently, consider ensuring the ProxyAction.ReadRawValue calls are efficient or cached appropriately; this implementation reads values on demand.