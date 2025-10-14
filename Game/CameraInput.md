# Game.CameraInput

**Assembly:**  
**Namespace:** Game

**Type:** class

**Base:** UnityEngine.MonoBehaviour

**Summary:** Handles reading and exposing camera-related input for movement, fast movement, rotation, and zoom. Uses the game's input action system (ProxyAction / InputManager) and provides smoothing parameters and simple boolean helpers to check input state.
---

## Fields

- `public float m_MoveSmoothing = 1E-06f`  
Small smoothing factor applied to camera movement. Default is 1e-6.

- `public float m_RotateSmoothing = 1E-06f`  
Small smoothing factor applied to camera rotation. Default is 1e-6.

- `public float m_ZoomSmoothing = 1E-06f`  
Small smoothing factor applied to camera zoom. Default is 1e-6.

- `private ProxyAction m_MoveAction`  
ProxyAction used to read standard camera move input. Populated in Initialize().

- `private ProxyAction m_FastMoveAction`  
ProxyAction used to read fast camera move input (e.g., when a "fast move" modifier is held). Populated in Initialize().

- `private ProxyAction m_RotateAction`  
ProxyAction used to read camera rotate input. Populated in Initialize().

- `private ProxyAction m_ZoomAction`  
ProxyAction used to read camera zoom input. Populated in Initialize().

## Properties

- `public Vector2 move { get; private set; }`  
Current camera move vector. Written during Refresh() by taking the component-wise max-abs between the normal move and fast-move actions.

- `public Vector2 rotate { get; private set; }`  
Current camera rotation input vector. Written in Refresh().

- `public float zoom { get; private set; }`  
Current camera zoom input value. Written in Refresh().

- `public bool isMoving => m_MoveAction.IsInProgress()`  
True when the standard move action is in progress. Note: fast-move is not considered by this property.

- `public bool any`  
True if any of the move, fast-move, rotate, or zoom actions are in progress. Evaluates each ProxyAction.IsInProgress() to determine overall activity.

## Constructors

- `public CameraInput()`  
Implicit default constructor provided by C#. No explicit initialization is performed here; call Initialize() to bind input actions and call Refresh() each frame (or when input should be sampled).

## Methods

- `public void Initialize()`  
Finds and caches the camera-related ProxyAction instances from the central InputManager. Must be called before Refresh() or checking properties that rely on the actions.

- `public void Refresh()`  
Reads current values from the cached ProxyAction objects and updates the move, rotate and zoom properties. Uses MathUtils.MaxAbs(...) to combine normal and fast-move inputs.

```csharp
public void Initialize()
{
	m_MoveAction = InputManager.instance.FindAction("Camera", "Move");
	m_FastMoveAction = InputManager.instance.FindAction("Camera", "Move Fast");
	m_RotateAction = InputManager.instance.FindAction("Camera", "Rotate");
	m_ZoomAction = InputManager.instance.FindAction("Camera", "Zoom");
}
```

```csharp
public void Refresh()
{
	move = MathUtils.MaxAbs(m_MoveAction.ReadValue<Vector2>(), m_FastMoveAction.ReadValue<Vector2>());
	rotate = m_RotateAction.ReadValue<Vector2>();
	zoom = m_ZoomAction.ReadValue<float>();
}
```

Notes and implementation details:
- This component expects InputManager.instance to be available and the named actions ("Camera"/"Move", "Move Fast", "Rotate", "Zoom") to be configured in the game's input system.
- MathUtils.MaxAbs takes two Vector2s and returns the vector that uses the element-wise value with the larger absolute value — used here to prioritize stronger directional input from either normal or fast move.
- Smoothing fields are present for use by consumers of this component but are not applied inside CameraInput itself; they are intended to be used by camera controllers when processing the raw move/rotate/zoom values.