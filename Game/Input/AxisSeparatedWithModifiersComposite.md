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
public override float EvaluateMagnitude(ref InputBindingCompositeContext context)
	{
		float num = ReadValue(ref context);
		if (num < midPoint)
		{
			num = Mathf.Abs(num - midPoint);
			return NormalizeProcessor.Normalize(num, 0f, Mathf.Abs(m_MinValue), 0f);
		}
		num = Mathf.Abs(num - midPoint);
		return NormalizeProcessor.Normalize(num, 0f, Mathf.Abs(m_MaxValue), 0f);
	}
```

- `public static GetCompositeData() : Game.Input.InputManager+CompositeData`  

```csharp
public static InputManager.CompositeData GetCompositeData()
	{
		return new InputManager.CompositeData(CompositeUtility.GetCompositeTypeName(typeof(AxisSeparatedWithModifiersComposite)), ActionType.Axis, new InputManager.CompositeComponentData[2]
		{
			new InputManager.CompositeComponentData(ActionComponent.Negative, "negative", "negativeModifier"),
			new InputManager.CompositeComponentData(ActionComponent.Positive, "positive", "positiveModifier")
		});
	}
```

- `public virtual ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context) : System.Single`  

```csharp
public override float ReadValue(ref InputBindingCompositeContext context)
	{
		if (m_IsDummy)
		{
			return 0f;
		}
		float num;
		float num2;
		if (m_Mode == Mode.Analog)
		{
			num = Mathf.Abs(CompositeUtility.ReadValue(ref context, negative, m_AllowModifiers, negativeModifier, DefaultComparer<float>.instance));
			num2 = Mathf.Abs(CompositeUtility.ReadValue(ref context, positive, m_AllowModifiers, positiveModifier, DefaultComparer<float>.instance));
		}
		else
		{
			num = (CompositeUtility.ReadValueAsButton(ref context, negative, m_AllowModifiers, negativeModifier) ? 1f : 0f);
			num2 = (CompositeUtility.ReadValueAsButton(ref context, positive, m_AllowModifiers, positiveModifier) ? 1f : 0f);
		}
		bool flag = num > Mathf.Epsilon;
		bool flag2 = num2 > Mathf.Epsilon;
		if (flag == flag2)
		{
			switch (m_WhichSideWins)
			{
			case WhichSideWins.Negative:
				flag2 = false;
				break;
			case WhichSideWins.Positive:
				flag = false;
				break;
			case WhichSideWins.Neither:
				return midPoint;
			}
		}
		float num3 = midPoint;
		if (flag)
		{
			return num3 - (num3 - m_MinValue) * num;
		}
		if (flag2)
		{
			return num3 + (m_MaxValue - num3) * num2;
		}
		return midPoint;
	}
```


## Nested types

- `Game.Input.AxisSeparatedWithModifiersComposite+WhichSideWins`  

