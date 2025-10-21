# Game.Input.SmoothVector2Processor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.SmoothProcessor<UnityEngine.Vector2>`  
**Implements:** `Game.Input.IDisableableProcessor`  

## Code

```csharp
public class SmoothVector2Processor : Game.Input.SmoothProcessor<UnityEngine.Vector2>, Game.Input.IDisableableProcessor
{
    private static const System.Single kDelta;

    public SmoothVector2Processor();

    protected virtual UnityEngine.Vector2 Smooth(UnityEngine.Vector2 value, UnityEngine.Vector2& lastValue, System.Single delta);
}
```


## Fields

- `private static const System.Single kDelta`  

```csharp
private static const System.Single kDelta;
```


## Constructors

- `public SmoothVector2Processor()`  

```csharp
public SmoothVector2Processor();
```


## Methods

- `protected virtual Smooth(UnityEngine.Vector2 value, UnityEngine.Vector2& lastValue, System.Single delta) : UnityEngine.Vector2`  

```csharp
protected virtual UnityEngine.Vector2 Smooth(UnityEngine.Vector2 value, UnityEngine.Vector2& lastValue, System.Single delta);
```


