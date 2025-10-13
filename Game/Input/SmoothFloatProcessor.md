# Game.Input.SmoothFloatProcessor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.SmoothProcessor<System.Single>`  
**Implements:** `Game.Input.IDisableableProcessor`  

## Code

```csharp
public class SmoothFloatProcessor : Game.Input.SmoothProcessor<System.Single>, Game.Input.IDisableableProcessor
{
    private static const System.Single kDelta;

    public SmoothFloatProcessor();

    protected virtual System.Single Smooth(System.Single value, System.Single& lastValue, System.Single delta);
}
```


## Fields

- `private static const System.Single kDelta`  

```csharp
private static const System.Single kDelta;
```


## Constructors

- `public SmoothFloatProcessor()`  

```csharp
public SmoothFloatProcessor();
```


## Methods

- `protected virtual Smooth(System.Single value, System.Single& lastValue, System.Single delta) : System.Single`  

```csharp
protected virtual System.Single Smooth(System.Single value, System.Single& lastValue, System.Single delta);
```


