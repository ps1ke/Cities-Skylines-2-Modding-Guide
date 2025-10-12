# Game.UI.InputBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Fields

- `private Game.CameraController m_CameraController`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_CameraMovingBinding`  
- `private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_CameraBarrierBinding`  
- `private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_ToolBarrierBinding`  
- `private readonly Colossal.UI.Binding.EventBinding<System.Boolean> m_ToolActionPerformedBinding`  
- `private Game.Input.InputBarrier m_CameraInputBarrier`  
- `private Game.Input.InputBarrier m_ToolInputBarrier`  
- `private static const System.String kGroup`  
- `private static const System.Single kCameraInputSensitivity`  
- `private static const System.Single kCameraInputSensitivitySqr`  

## Constructors

- `public InputBindings()`  

## Methods

- `public Dispose() : System.Void`  
- `private OnGamepadPointerEvent(System.Boolean pointerOverUI) : System.Void`  
- `private OnToolActionPerformed(Game.Input.ProxyAction action) : System.Void`  
- `private SetActiveTextfieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Void`  
- `public virtual Update() : System.Boolean`  

## Nested types

- `Game.UI.InputBindings+<>c`  

