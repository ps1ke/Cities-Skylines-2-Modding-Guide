# Game.Debug.IntInputField

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.DebugUI+TextField`  
**Implements:** `UnityEngine.Rendering.DebugUI+IValueField`  

## Code

```csharp
public class IntInputField : UnityEngine.Rendering.DebugUI+TextField, UnityEngine.Rendering.DebugUI+IValueField
{
    public IntInputField();

    public virtual System.String ValidateValue(System.String value);
}
```


## Constructors

- `public IntInputField()`  

```csharp
public IntInputField();
```


## Methods

- `public virtual ValidateValue(System.String value) : System.String`  

```csharp
public override string ValidateValue(string value)
	{
		if (string.IsNullOrEmpty(value) || int.TryParse(value, out var _))
		{
			return value;
		}
		return base.getter();
	}
```


