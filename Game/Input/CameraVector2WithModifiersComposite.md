# Game.Input.CameraVector2WithModifiersComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.AnalogValueInputBindingComposite<UnityEngine.Vector2>`  
**Implements:** `Game.Input.ICustomComposite`  

**Attributes:** `DisplayStringFormat`, `DisplayName`  

## Code

```csharp
public class CameraVector2WithModifiersComposite : Game.Input.AnalogValueInputBindingComposite<UnityEngine.Vector2>, Game.Input.ICustomComposite
{
    public System.Boolean m_ModifierActuatesControl;
    public System.Int32 vector;
    public System.Int32 trigger;

    public CameraVector2WithModifiersComposite();

    public virtual System.Single EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context);
    public static Game.Input.InputManager+CompositeData GetCompositeData();
    public virtual UnityEngine.Vector2 ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context);
}
```


## Fields

- `public System.Boolean m_ModifierActuatesControl`  

```csharp
public System.Boolean m_ModifierActuatesControl;
```

- `public System.Int32 vector`  

```csharp
public System.Int32 vector;
```

- `public System.Int32 trigger`  

```csharp
public System.Int32 trigger;
```


## Constructors

- `public CameraVector2WithModifiersComposite()`  

```csharp
public CameraVector2WithModifiersComposite();
```


## Methods

- `public virtual EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context) : System.Single`  

```csharp
public virtual System.Single EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context);
```

- `public static GetCompositeData() : Game.Input.InputManager+CompositeData`  

```csharp
public static Game.Input.InputManager+CompositeData GetCompositeData();
```

- `public virtual ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context) : UnityEngine.Vector2`  

```csharp
public virtual UnityEngine.Vector2 ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context);
```


