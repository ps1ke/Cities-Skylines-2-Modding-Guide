# Game.Input.AxisWithModifiersComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.AnalogValueInputBindingComposite<System.Single>`  
**Implements:** `Game.Input.ICustomComposite`  

**Attributes:** `DisplayStringFormat`, `DisplayName`  

## Code

```csharp
public class AxisWithModifiersComposite : Game.Input.AnalogValueInputBindingComposite<System.Single>, Game.Input.ICustomComposite
{
    public System.Int32 binding;
    public System.Int32 modifier;

    public AxisWithModifiersComposite();

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

- `public AxisWithModifiersComposite()`  

```csharp
public AxisWithModifiersComposite();
```


## Methods

- `public virtual EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context) : System.Single`  

```csharp
public override float EvaluateMagnitude(ref InputBindingCompositeContext context)
	{
		return Mathf.Abs(ReadValue(ref context));
	}
```

- `public static GetCompositeData() : Game.Input.InputManager+CompositeData`  

```csharp
public static InputManager.CompositeData GetCompositeData()
	{
		return new InputManager.CompositeData(CompositeUtility.GetCompositeTypeName(typeof(AxisWithModifiersComposite)), ActionType.Button, new InputManager.CompositeComponentData[1]
		{
			new InputManager.CompositeComponentData(ActionComponent.Press, "binding", "modifier")
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
		if (m_Mode == Mode.Analog)
		{
			return CompositeUtility.ReadValue(ref context, binding, base.allowModifiers, modifier, DefaultComparer<float>.instance);
		}
		if (!CompositeUtility.ReadValueAsButton(ref context, binding, base.allowModifiers, modifier))
		{
			return 0f;
		}
		return 1f;
	}
```


