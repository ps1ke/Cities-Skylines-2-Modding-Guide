# Game.Input.Vector2SeparatedWithModifiersComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.AnalogValueInputBindingComposite<UnityEngine.Vector2>`  
**Implements:** `Game.Input.ICustomComposite`  

**Attributes:** `DisplayStringFormat`, `DisplayName`  

## Code

```csharp
public class Vector2SeparatedWithModifiersComposite : Game.Input.AnalogValueInputBindingComposite<UnityEngine.Vector2>, Game.Input.ICustomComposite
{
    public System.Int32 up;
    public System.Int32 down;
    public System.Int32 left;
    public System.Int32 right;
    public System.Int32 upModifier;
    public System.Int32 downModifier;
    public System.Int32 leftModifier;
    public System.Int32 rightModifier;

    public Vector2SeparatedWithModifiersComposite();

    public virtual System.Single EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context);
    public static Game.Input.InputManager+CompositeData GetCompositeData();
    public virtual UnityEngine.Vector2 ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context);
}
```


## Fields

- `public System.Int32 up`  

```csharp
public System.Int32 up;
```

- `public System.Int32 down`  

```csharp
public System.Int32 down;
```

- `public System.Int32 left`  

```csharp
public System.Int32 left;
```

- `public System.Int32 right`  

```csharp
public System.Int32 right;
```

- `public System.Int32 upModifier`  

```csharp
public System.Int32 upModifier;
```

- `public System.Int32 downModifier`  

```csharp
public System.Int32 downModifier;
```

- `public System.Int32 leftModifier`  

```csharp
public System.Int32 leftModifier;
```

- `public System.Int32 rightModifier`  

```csharp
public System.Int32 rightModifier;
```


## Constructors

- `public Vector2SeparatedWithModifiersComposite()`  

```csharp
public Vector2SeparatedWithModifiersComposite();
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


