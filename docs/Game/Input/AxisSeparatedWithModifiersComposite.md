# Game.Input.AxisSeparatedWithModifiersComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.AnalogValueInputBindingComposite<System.Single>`  
**Implements:** `Game.Input.ICustomComposite`  

**Attributes:** `DisplayStringFormat`, `DisplayName`  

## Fields

- `public System.Int32 negative`  
- `public System.Int32 positive`  
- `public System.Int32 negativeModifier`  
- `public System.Int32 positiveModifier`  
- `public System.Single m_MinValue`  
- `public System.Single m_MaxValue`  
- `public Game.Input.AxisSeparatedWithModifiersComposite+WhichSideWins m_WhichSideWins`  

## Properties

- `public System.Single midPoint { get }`  

## Constructors

- `public AxisSeparatedWithModifiersComposite()`  

## Methods

- `public virtual EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context) : System.Single`  
- `public static GetCompositeData() : Game.Input.InputManager+CompositeData`  
- `public virtual ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context) : System.Single`  

## Nested types

- `Game.Input.AxisSeparatedWithModifiersComposite+WhichSideWins`  

