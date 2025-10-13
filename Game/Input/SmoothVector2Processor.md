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
protected override Vector2 Smooth(Vector2 value, ref Vector2 lastValue, float delta)
	{
		if (m_Smoothing > 0f)
		{
			float t = Mathf.Pow(m_Smoothing, delta);
			value = Vector2.Lerp(value, lastValue, t);
			if (value.sqrMagnitude < 1E-12f)
			{
				value = Vector2.zero;
			}
		}
		lastValue = value;
		if (m_Time)
		{
			value *= Time.deltaTime;
		}
		return value;
	}
```


