# Game.Input.CompositeUtility

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class CompositeUtility
{
    public static System.Boolean CheckModifiers(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Boolean allowModifiers, System.Int32 modifier);
    public static Game.Input.ActionType GetActionType(Game.Input.ActionComponent component);
    public static System.String GetCompositeTypeName(Game.Input.ActionType actionType);
    public static System.String GetCompositeTypeName(System.Type type);
    public static System.String GetExpectedControlLayout(Game.Input.ActionType actionType);
    public static System.Guid GetGuid(System.Int64 part1, System.Int64 part2);
    public static UnityEngine.InputSystem.InputActionType GetInputActionType(Game.Input.ActionType actionType);
    public static T ReadValue<T>(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier, System.Collections.Generic.IComparer<T> comparer);
    public static System.Boolean ReadValueAsButton(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier);
    public static System.Void SetGuid(System.Guid guid, System.Int64& part1, System.Int64& part2);
}
```


## Methods

- `public static CheckModifiers(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Boolean allowModifiers, System.Int32 modifier) : System.Boolean`  

```csharp
public static bool CheckModifiers(ref InputBindingCompositeContext context, bool allowModifiers, int modifier)
	{
		float num = ((allowModifiers && modifier != 0) ? context.ReadValue<float, ModifiersComparer>(modifier) : 1f);
		if (!float.IsNaN(num))
		{
			return num != 0f;
		}
		return false;
	}
```

- `public static GetActionType(Game.Input.ActionComponent component) : Game.Input.ActionType`  

```csharp
public static ActionType GetActionType(this ActionComponent component)
	{
		return component switch
		{
			ActionComponent.Press => ActionType.Button, 
			ActionComponent.Negative => ActionType.Axis, 
			ActionComponent.Positive => ActionType.Axis, 
			ActionComponent.Down => ActionType.Vector2, 
			ActionComponent.Up => ActionType.Vector2, 
			ActionComponent.Left => ActionType.Vector2, 
			ActionComponent.Right => ActionType.Vector2, 
			_ => throw new ArgumentOutOfRangeException("component", component, null), 
		};
	}
```

- `public static GetCompositeTypeName(Game.Input.ActionType actionType) : System.String`  

```csharp
public static string GetCompositeTypeName(Type type)
	{
		string text = type.Name;
		if (text.EndsWith("Composite"))
		{
			text = text.Substring(0, text.Length - "Composite".Length);
		}
		return text;
	}
```

- `public static GetCompositeTypeName(System.Type type) : System.String`  

```csharp
public static string GetCompositeTypeName(Type type)
	{
		string text = type.Name;
		if (text.EndsWith("Composite"))
		{
			text = text.Substring(0, text.Length - "Composite".Length);
		}
		return text;
	}
```

- `public static GetExpectedControlLayout(Game.Input.ActionType actionType) : System.String`  

```csharp
public static string GetExpectedControlLayout(this ActionType actionType)
	{
		return actionType switch
		{
			ActionType.Button => "Button", 
			ActionType.Axis => "Axis", 
			ActionType.Vector2 => "Vector2", 
			_ => throw new ArgumentOutOfRangeException("actionType", actionType, null), 
		};
	}
```

- `public static GetGuid(System.Int64 part1, System.Int64 part2) : System.Guid`  

```csharp
public static Guid GetGuid(long part1, long part2)
	{
		byte[] array = new byte[16];
		Array.Copy(BitConverter.GetBytes(part1), 0, array, 0, 8);
		Array.Copy(BitConverter.GetBytes(part2), 0, array, 8, 8);
		return new Guid(array);
	}
```

- `public static GetInputActionType(Game.Input.ActionType actionType) : UnityEngine.InputSystem.InputActionType`  

```csharp
public static InputActionType GetInputActionType(this ActionType actionType)
	{
		return actionType switch
		{
			ActionType.Button => InputActionType.Button, 
			ActionType.Axis => InputActionType.Value, 
			ActionType.Vector2 => InputActionType.Value, 
			_ => throw new ArgumentOutOfRangeException("actionType", actionType, null), 
		};
	}
```

- `public static ReadValue<T>(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier, System.Collections.Generic.IComparer<T> comparer) : T`  

```csharp
public static T ReadValue<T>(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier, System.Collections.Generic.IComparer<T> comparer);
```

- `public static ReadValueAsButton(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier) : System.Boolean`  

```csharp
public static bool ReadValueAsButton(ref InputBindingCompositeContext context, int button, bool allowModifiers, int modifier)
	{
		if (context.m_State != null && CheckModifiers(ref context, allowModifiers, modifier))
		{
			return context.ReadValueAsButton(button);
		}
		return false;
	}
```

- `public static SetGuid(System.Guid guid, System.Int64& part1, System.Int64& part2) : System.Void`  

```csharp
public static void SetGuid(Guid guid, out long part1, out long part2)
	{
		byte[] value = guid.ToByteArray();
		part1 = BitConverter.ToInt64(value, 0);
		part2 = BitConverter.ToInt64(value, 8);
	}
```


