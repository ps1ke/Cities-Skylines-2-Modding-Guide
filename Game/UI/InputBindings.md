# Game.UI.InputBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class InputBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private Game.CameraController m_CameraController;
    private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_CameraMovingBinding;
    private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_CameraBarrierBinding;
    private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_ToolBarrierBinding;
    private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_ToolActionPerformedBinding;
    private Game.Input.InputBarrier m_CameraInputBarrier;
    private Game.Input.InputBarrier m_ToolInputBarrier;
    private static const System.String kGroup;
    private static const System.Single kCameraInputSensitivity;
    private static const System.Single kCameraInputSensitivitySqr;

    public InputBindings();

    public System.Void Dispose();
    private System.Void OnGamepadPointerEvent(System.Boolean pointerOverUI);
    private System.Void OnToolActionPerformed(Game.Input.ProxyAction action);
    private System.Void SetActiveTextfieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
    public virtual System.Boolean Update();
}
```


## Fields

- `private Game.CameraController m_CameraController`  

```csharp
private Game.CameraController m_CameraController;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_CameraMovingBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_CameraMovingBinding;
```

- `private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_CameraBarrierBinding`  

```csharp
private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_CameraBarrierBinding;
```

- `private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_ToolBarrierBinding`  

```csharp
private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_ToolBarrierBinding;
```

- `private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_ToolActionPerformedBinding`  

```csharp
private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_ToolActionPerformedBinding;
```

- `private Game.Input.InputBarrier m_CameraInputBarrier`  

```csharp
private Game.Input.InputBarrier m_CameraInputBarrier;
```

- `private Game.Input.InputBarrier m_ToolInputBarrier`  

```csharp
private Game.Input.InputBarrier m_ToolInputBarrier;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.Single kCameraInputSensitivity`  

```csharp
private static const System.Single kCameraInputSensitivity;
```

- `private static const System.Single kCameraInputSensitivitySqr`  

```csharp
private static const System.Single kCameraInputSensitivitySqr;
```


## Constructors

- `public InputBindings()`  

```csharp
public InputBindings()
	{
		AddUpdateBinding(new GetterValueBinding<bool>("input", "mouseOverUI", () => InputManager.instance.mouseOverUI));
		AddUpdateBinding(new GetterValueBinding<bool>("input", "hideCursor", () => InputManager.instance.hideCursor));
		AddUpdateBinding(new GetterValueBinding<int>("input", "controlScheme", () => (int)InputManager.instance.activeControlScheme));
		AddUpdateBinding(new GetterValueBinding<float>("input", "scrollSensitivity", () => SharedSettings.instance.input.finalScrollSensitivity));
		AddUpdateBinding(new GetterValueBinding<Vector2>("input", "gamepadPointerPosition", () => InputManager.instance.gamepadPointerPosition));
		AddBinding(m_CameraMovingBinding = new ValueBinding<bool>("input", "cameraMoving", initialValue: false));
		AddBinding(m_ToolActionPerformedBinding = new EventBinding<bool>("input", "toolActionPerformed"));
		AddBinding(m_CameraBarrierBinding = new EventBinding<bool>("input", "cameraBarrier"));
		AddBinding(m_ToolBarrierBinding = new EventBinding<bool>("input", "toolBarrier"));
		AddBinding(new TriggerBinding<bool>("input", "onGamepadPointerEvent", OnGamepadPointerEvent));
		AddBinding(new TriggerBinding<int, int, int, int>("input", "setActiveTextFieldRect", SetActiveTextfieldRect));
		AddBinding(new GetterValueBinding<bool>("input", "useTextFieldInputBarrier", () => PlatformManager.instance.passThroughVKeyboard));
		m_CameraInputBarrier = InputManager.instance.CreateMapBarrier("Camera", "InputBindings");
		m_ToolInputBarrier = InputManager.instance.CreateMapBarrier("Tool", "InputBindings");
		ToolBaseSystem.EventToolActionPerformed += OnToolActionPerformed;
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_CameraInputBarrier.Dispose();
		m_ToolInputBarrier.Dispose();
		ToolBaseSystem.EventToolActionPerformed -= OnToolActionPerformed;
	}
```

- `private OnGamepadPointerEvent(System.Boolean pointerOverUI) : System.Void`  

```csharp
private void OnGamepadPointerEvent(bool pointerOverUI)
	{
		InputManager.instance.mouseOverUI = pointerOverUI;
	}
```

- `private OnToolActionPerformed(Game.Input.ProxyAction action) : System.Void`  

```csharp
private void OnToolActionPerformed(ProxyAction action)
	{
		m_ToolActionPerformedBinding.Trigger(value: true);
	}
```

- `private SetActiveTextfieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Void`  

```csharp
private void SetActiveTextfieldRect(int x, int y, int width, int height)
	{
		PlatformManager.instance?.SetActiveTextFieldRect(x, y, width, height);
	}
```

- `public virtual Update() : System.Boolean`  

```csharp
public override bool Update()
	{
		bool newValue = false;
		if (m_CameraController != null || CameraController.TryGet(out m_CameraController))
		{
			foreach (ProxyAction inputAction in m_CameraController.inputActions)
			{
				if (!inputAction.IsInProgress())
				{
					continue;
				}
				Type valueType = inputAction.valueType;
				if (valueType == typeof(float))
				{
					if (Mathf.Abs(inputAction.ReadRawValue<float>()) >= 0.2f)
					{
						newValue = true;
						break;
					}
				}
				else if (valueType == typeof(Vector2) && inputAction.ReadRawValue<Vector2>().sqrMagnitude >= 0.040000003f)
				{
					newValue = true;
					break;
				}
			}
		}
		m_CameraMovingBinding.Update(newValue);
		m_CameraInputBarrier.blocked = m_CameraBarrierBinding.observerCount > 0;
		m_ToolInputBarrier.blocked = m_ToolBarrierBinding.observerCount > 0;
		return base.Update();
	}
```


## Nested types

- `Game.UI.InputBindings+<>c`  

