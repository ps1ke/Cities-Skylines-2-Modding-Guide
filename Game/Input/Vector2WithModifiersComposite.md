# Game.Input.Vector2WithModifiersComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.AnalogValueInputBindingComposite<UnityEngine.Vector2>`  
**Implements:** `Game.Input.ICustomComposite`  

**Attributes:** `DisplayStringFormat`, `DisplayName`  

## Code

```csharp
public class Vector2WithModifiersComposite : Game.Input.AnalogValueInputBindingComposite<UnityEngine.Vector2>, Game.Input.ICustomComposite
{
    public System.Int32 binding;
    public System.Int32 modifier;

    public Vector2WithModifiersComposite();

    public virtual System.Single EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context);
    public static Game.Input.InputManager+CompositeData GetCompositeData();
    public virtual UnityEngine.Vector2 ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context);
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

- `public Vector2WithModifiersComposite()`  

```csharp
public Vector2WithModifiersComposite();
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
		return new InputManager.CompositeData(CompositeUtility.GetCompositeTypeName(typeof(Vector2WithModifiersComposite)), ActionType.Button, new InputManager.CompositeComponentData[1]
		{
			new InputManager.CompositeComponentData(ActionComponent.Press, "binding", "modifier")
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
			return CompositeUtility.ReadValue(ref context, binding, base.allowModifiers, modifier, Vector2Comparer.instance);
		}
		if (!CompositeUtility.ReadValueAsButton(ref context, binding, base.allowModifiers, modifier))
		{
			return Vector2.zero;
		}
		return Vector2.one;
	}
```


