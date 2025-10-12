# Game.Input.DeviceListener

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `UnityEngine.InputSystem.LowLevel.IInputStateChangeMonitor`, `System.IDisposable`  

## Fields

- `private System.Collections.Generic.List<UnityEngine.InputSystem.InputControl> m_Controls`  
- `private System.Boolean m_Listening`  
- `private System.Single m_RequiredDelta`  
- `private System.Single m_Delta`  
- `private System.Boolean m_Activated`  
- `public Game.Input.DeviceListener+DeviceEvent EventDeviceActivated`  
- `private UnityEngine.InputSystem.InputDevice <device>k__BackingField`  

## Properties

- `public UnityEngine.InputSystem.InputDevice device { get; private set }`  

## Constructors

- `public DeviceListener(UnityEngine.InputSystem.InputDevice device, System.Single requiredDelta)`  

## Methods

- `public Dispose() : System.Void`  
- `public NotifyControlStateChanged(UnityEngine.InputSystem.InputControl control, System.Double time, UnityEngine.InputSystem.LowLevel.InputEventPtr eventPtr, System.Int64 monitorIndex) : System.Void`  
- `public NotifyTimerExpired(UnityEngine.InputSystem.InputControl control, System.Double time, System.Int64 monitorIndex, System.Int32 timerIndex) : System.Void`  
- `public StartListening() : System.Void`  
- `public StopListening() : System.Void`  
- `public Tick() : System.Void`  
- `private ValidateControl(UnityEngine.InputSystem.InputControl control) : System.Boolean`  

## Nested types

- `Game.Input.DeviceListener+DeviceEvent`  

