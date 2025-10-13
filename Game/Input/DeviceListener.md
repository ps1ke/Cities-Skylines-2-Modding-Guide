# Game.Input.DeviceListener

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `UnityEngine.InputSystem.LowLevel.IInputStateChangeMonitor`, `System.IDisposable`  

## Code

```csharp
public class DeviceListener : UnityEngine.InputSystem.LowLevel.IInputStateChangeMonitor, System.IDisposable
{
    private System.Collections.Generic.List<UnityEngine.InputSystem.InputControl> m_Controls;
    private System.Boolean m_Listening;
    private System.Single m_RequiredDelta;
    private System.Single m_Delta;
    private System.Boolean m_Activated;
    public Game.Input.DeviceListener+DeviceEvent EventDeviceActivated;
    private UnityEngine.InputSystem.InputDevice <device>k__BackingField;

    public UnityEngine.InputSystem.InputDevice device { get; private set; }

    public DeviceListener(UnityEngine.InputSystem.InputDevice device, System.Single requiredDelta);

    public System.Void Dispose();
    public System.Void NotifyControlStateChanged(UnityEngine.InputSystem.InputControl control, System.Double time, UnityEngine.InputSystem.LowLevel.InputEventPtr eventPtr, System.Int64 monitorIndex);
    public System.Void NotifyTimerExpired(UnityEngine.InputSystem.InputControl control, System.Double time, System.Int64 monitorIndex, System.Int32 timerIndex);
    public System.Void StartListening();
    public System.Void StopListening();
    public System.Void Tick();
    private System.Boolean ValidateControl(UnityEngine.InputSystem.InputControl control);
}
```


## Fields

- `private System.Collections.Generic.List<UnityEngine.InputSystem.InputControl> m_Controls`  

```csharp
private System.Collections.Generic.List<UnityEngine.InputSystem.InputControl> m_Controls;
```

- `private System.Boolean m_Listening`  

```csharp
private System.Boolean m_Listening;
```

- `private System.Single m_RequiredDelta`  

```csharp
private System.Single m_RequiredDelta;
```

- `private System.Single m_Delta`  

```csharp
private System.Single m_Delta;
```

- `private System.Boolean m_Activated`  

```csharp
private System.Boolean m_Activated;
```

- `public Game.Input.DeviceListener+DeviceEvent EventDeviceActivated`  

```csharp
public Game.Input.DeviceListener+DeviceEvent EventDeviceActivated;
```

- `private UnityEngine.InputSystem.InputDevice <device>k__BackingField`  

```csharp
private UnityEngine.InputSystem.InputDevice <device>k__BackingField;
```


## Properties

- `public UnityEngine.InputSystem.InputDevice device { get; private set }`  

```csharp
public UnityEngine.InputSystem.InputDevice device { get; private set; }
```


## Constructors

- `public DeviceListener(UnityEngine.InputSystem.InputDevice device, System.Single requiredDelta)`  

```csharp
public DeviceListener(InputDevice device, float requiredDelta)
	{
		EventDeviceActivated = new DeviceEvent();
		this.device = device;
		m_Controls = new List<InputControl>();
		m_RequiredDelta = requiredDelta;
		foreach (InputControl allControl in device.allControls)
		{
			if (ValidateControl(allControl))
			{
				m_Controls.Add(allControl);
			}
		}
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		StopListening();
	}
```

- `public NotifyControlStateChanged(UnityEngine.InputSystem.InputControl control, System.Double time, UnityEngine.InputSystem.LowLevel.InputEventPtr eventPtr, System.Int64 monitorIndex) : System.Void`  

```csharp
public void NotifyControlStateChanged(InputControl control, double time, InputEventPtr eventPtr, long monitorIndex)
	{
		if (control is ButtonControl && ((ButtonControl)control).wasPressedThisFrame)
		{
			m_Activated = true;
		}
	}
```

- `public NotifyTimerExpired(UnityEngine.InputSystem.InputControl control, System.Double time, System.Int64 monitorIndex, System.Int32 timerIndex) : System.Void`  

```csharp
public void NotifyTimerExpired(InputControl control, double time, long monitorIndex, int timerIndex)
	{
	}
```

- `public StartListening() : System.Void`  

```csharp
public void StartListening()
	{
		if (m_Listening)
		{
			return;
		}
		m_Activated = false;
		m_Listening = true;
		m_Delta = 0f;
		foreach (InputControl control in m_Controls)
		{
			InputState.AddChangeMonitor(control, this, -1L);
		}
	}
```

- `public StopListening() : System.Void`  

```csharp
public void StopListening()
	{
		if (!m_Listening)
		{
			return;
		}
		m_Activated = false;
		m_Listening = false;
		m_Delta = 0f;
		foreach (InputControl control in m_Controls)
		{
			InputState.RemoveChangeMonitor(control, this, -1L);
		}
	}
```

- `public Tick() : System.Void`  

```csharp
public void Tick()
	{
		m_Delta = Math.Max(m_Delta - Time.deltaTime, 0f);
		if (m_Activated)
		{
			m_Activated = false;
			EventDeviceActivated?.Invoke(device);
		}
	}
```

- `private ValidateControl(UnityEngine.InputSystem.InputControl control) : System.Boolean`  

```csharp
private bool ValidateControl(InputControl control)
	{
		if (control is ButtonControl)
		{
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.Input.DeviceListener+DeviceEvent`  

