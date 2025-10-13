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
public InputBindings();
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private OnGamepadPointerEvent(System.Boolean pointerOverUI) : System.Void`  

```csharp
private System.Void OnGamepadPointerEvent(System.Boolean pointerOverUI);
```

- `private OnToolActionPerformed(Game.Input.ProxyAction action) : System.Void`  

```csharp
private System.Void OnToolActionPerformed(Game.Input.ProxyAction action);
```

- `private SetActiveTextfieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Void`  

```csharp
private System.Void SetActiveTextfieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
```

- `public virtual Update() : System.Boolean`  

```csharp
public virtual System.Boolean Update();
```


## Nested types

- `Game.UI.InputBindings+<>c`  

