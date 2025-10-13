# Game.Input.ButtonWithModifiersComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.AnalogValueInputBindingComposite<System.Single>`  
**Implements:** `Game.Input.ICustomComposite`  

**Attributes:** `DisplayStringFormat`, `DisplayName`  

## Code

```csharp
public class ButtonWithModifiersComposite : Game.Input.AnalogValueInputBindingComposite<System.Single>, Game.Input.ICustomComposite
{
    public System.Int32 binding;
    public System.Int32 modifier;

    public ButtonWithModifiersComposite();

    public virtual System.Single EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context);
    public static Game.Input.InputManager+CompositeData GetCompositeData();
    public virtual System.Single ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context);
}
```


## Fields

- `public System.Int32 binding`  

```csharp
public System.Int32 binding;
```

- `public System.Int32 modifier`  

```csharp
public System.Int32 modifier;
```


## Constructors

- `public ButtonWithModifiersComposite()`  

```csharp
public ButtonWithModifiersComposite();
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

- `public virtual ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context) : System.Single`  

```csharp
public virtual System.Single ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context);
```


