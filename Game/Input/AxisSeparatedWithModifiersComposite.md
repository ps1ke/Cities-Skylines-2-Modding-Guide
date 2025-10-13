# Game.Input.AxisSeparatedWithModifiersComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.AnalogValueInputBindingComposite<System.Single>`  
**Implements:** `Game.Input.ICustomComposite`  

**Attributes:** `DisplayStringFormat`, `DisplayName`  

## Code

```csharp
public class AxisSeparatedWithModifiersComposite : Game.Input.AnalogValueInputBindingComposite<System.Single>, Game.Input.ICustomComposite
{
    public System.Int32 negative;
    public System.Int32 positive;
    public System.Int32 negativeModifier;
    public System.Int32 positiveModifier;
    public System.Single m_MinValue;
    public System.Single m_MaxValue;
    public Game.Input.AxisSeparatedWithModifiersComposite+WhichSideWins m_WhichSideWins;

    public System.Single midPoint { get; }

    public AxisSeparatedWithModifiersComposite();

    public virtual System.Single EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context);
    public static Game.Input.InputManager+CompositeData GetCompositeData();
    public virtual System.Single ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context);
}
```


## Fields

- `public System.Int32 negative`  

```csharp
public System.Int32 negative;
```

- `public System.Int32 positive`  

```csharp
public System.Int32 positive;
```

- `public System.Int32 negativeModifier`  

```csharp
public System.Int32 negativeModifier;
```

- `public System.Int32 positiveModifier`  

```csharp
public System.Int32 positiveModifier;
```

- `public System.Single m_MinValue`  

```csharp
public System.Single m_MinValue;
```

- `public System.Single m_MaxValue`  

```csharp
public System.Single m_MaxValue;
```

- `public Game.Input.AxisSeparatedWithModifiersComposite+WhichSideWins m_WhichSideWins`  

```csharp
public Game.Input.AxisSeparatedWithModifiersComposite+WhichSideWins m_WhichSideWins;
```


## Properties

- `public System.Single midPoint { get }`  

```csharp
public System.Single midPoint { get; }
```


## Constructors

- `public AxisSeparatedWithModifiersComposite()`  

```csharp
public AxisSeparatedWithModifiersComposite();
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


## Nested types

- `Game.Input.AxisSeparatedWithModifiersComposite+WhichSideWins`  

