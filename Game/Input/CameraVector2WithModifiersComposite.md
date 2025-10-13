# Game.Input.CameraVector2WithModifiersComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.AnalogValueInputBindingComposite<UnityEngine.Vector2>`  
**Implements:** `Game.Input.ICustomComposite`  

**Attributes:** `DisplayStringFormat`, `DisplayName`  

## Code

```csharp
public class CameraVector2WithModifiersComposite : Game.Input.AnalogValueInputBindingComposite<UnityEngine.Vector2>, Game.Input.ICustomComposite
{
    public System.Boolean m_ModifierActuatesControl;
    public System.Int32 vector;
    public System.Int32 trigger;

    public CameraVector2WithModifiersComposite();

    public virtual System.Single EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context);
    public static Game.Input.InputManager+CompositeData GetCompositeData();
    public virtual UnityEngine.Vector2 ReadValue(UnityEngine.InputSystem.InputBindingCompositeContext& context);
}
```


## Fields

- `public System.Boolean m_ModifierActuatesControl`  

```csharp
public System.Boolean m_ModifierActuatesControl;
```

- `public System.Int32 vector`  

```csharp
public System.Int32 vector;
```

- `public System.Int32 trigger`  

```csharp
public System.Int32 trigger;
```


## Constructors

- `public CameraVector2WithModifiersComposite()`  

```csharp
public CameraVector2WithModifiersComposite();
```


## Methods

- `public virtual EvaluateMagnitude(UnityEngine.InputSystem.InputBindingCompositeContext& context) : System.Single`  

```csharp
public override float EvaluateMagnitude(ref InputBindingCompositeContext context)
	{
		if (CompositeUtility.CheckModifiers(ref context, allowModifiers: true, trigger))
		{
			if (m_ModifierActuatesControl && trigger != 0)
			{
				return Mathf.Abs(context.ReadValue<float, ModifiersComparer>(trigger));
			}
			return context.EvaluateMagnitude(vector);
		}
		return 0f;
	}
```

- `public static GetCompositeData() : Game.Input.InputManager+CompositeData`  

```csharp
public static InputManager.CompositeData GetCompositeData()
	{
		return new InputManager.CompositeData(CompositeUtility.GetCompositeTypeName(typeof(CameraVector2WithModifiersComposite)), ActionType.Button, new InputManager.CompositeComponentData[1]
		{
			new InputManager.CompositeComponentData(ActionComponent.Press, "trigger", string.Empty)
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
			return CompositeUtility.ReadValue(ref context, vector, allowModifiers: true, trigger, Vector2Comparer.instance);
		}
		if (!CompositeUtility.ReadValueAsButton(ref context, vector, allowModifiers: true, trigger))
		{
			return Vector2.zero;
		}
		return Vector2.one;
	}
```


