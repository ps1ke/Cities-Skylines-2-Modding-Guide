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
public override float EvaluateMagnitude(ref InputBindingCompositeContext context)
	{
		return ReadValue(ref context).magnitude;
	}
```

- `public static GetCompositeData() : Game.Input.InputManager+CompositeData`  

```csharp
public static InputManager.CompositeData GetCompositeData()
	{
		return new InputManager.CompositeData(CompositeUtility.GetCompositeTypeName(typeof(Vector2SeparatedWithModifiersComposite)), ActionType.Vector2, new InputManager.CompositeComponentData[4]
		{
			new InputManager.CompositeComponentData(ActionComponent.Up, "up", "upModifier"),
			new InputManager.CompositeComponentData(ActionComponent.Down, "down", "downModifier"),
			new InputManager.CompositeComponentData(ActionComponent.Left, "left", "leftModifier"),
			new InputManager.CompositeComponentData(ActionComponent.Right, "right", "rightModifier")
		});
	}
```

- `public virtual ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context) : UnityEngine.Vector2`  

```csharp
public override Vector2 ReadValue(ref InputBindingCompositeContext context)
	{
		if (m_IsDummy)
		{
			return default(Vector2);
		}
		if (m_Mode == Mode.Analog)
		{
			float num = CompositeUtility.ReadValue(ref context, up, m_AllowModifiers, upModifier, DefaultComparer<float>.instance);
			float num2 = CompositeUtility.ReadValue(ref context, down, m_AllowModifiers, downModifier, DefaultComparer<float>.instance);
			float num3 = CompositeUtility.ReadValue(ref context, left, m_AllowModifiers, leftModifier, DefaultComparer<float>.instance);
			float num4 = CompositeUtility.ReadValue(ref context, right, m_AllowModifiers, rightModifier, DefaultComparer<float>.instance);
			return DpadControl.MakeDpadVector(num, num2, num3, num4);
		}
		bool num5 = CompositeUtility.ReadValueAsButton(ref context, up, m_AllowModifiers, upModifier);
		bool flag = CompositeUtility.ReadValueAsButton(ref context, down, m_AllowModifiers, downModifier);
		bool flag2 = CompositeUtility.ReadValueAsButton(ref context, left, m_AllowModifiers, leftModifier);
		bool flag3 = CompositeUtility.ReadValueAsButton(ref context, right, m_AllowModifiers, rightModifier);
		return DpadControl.MakeDpadVector(num5, flag, flag2, flag3, m_Mode == Mode.DigitalNormalized);
	}
```


