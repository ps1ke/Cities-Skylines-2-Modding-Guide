# Game.InputExtensions

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class InputExtensions
{
    public static System.Boolean ForEachCompositeOfAction(UnityEngine.InputSystem.InputAction inputAction, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax startIterator, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& endIterator);
    public static System.Boolean ForEachCompositeOfAction(UnityEngine.InputSystem.InputAction inputAction, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action);
    public static System.Boolean ForEachPartOfCompositeWithName(UnityEngine.InputSystem.InputAction inputAction, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax startIterator, System.String partName, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& endIterator);
    public static System.Boolean ForEachPartOfCompositeWithName(UnityEngine.InputSystem.InputAction inputAction, System.String partName, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action);
    public static System.Boolean TryGetCompositeOfActionWithName(UnityEngine.InputSystem.InputAction action, System.String compositeName, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& iterator);
    public static System.Boolean TryGetFirstCompositeOfAction(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& iterator);
}
```


## Methods

- `public static ForEachCompositeOfAction(UnityEngine.InputSystem.InputAction inputAction, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax startIterator, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& endIterator) : System.Boolean`  

```csharp
public static bool ForEachCompositeOfAction(this InputAction inputAction, Func<InputActionSetupExtensions.BindingSyntax, bool> action)
	{
		if (action == null)
		{
			return false;
		}
		if (!inputAction.TryGetFirstCompositeOfAction(out var iterator))
		{
			return false;
		}
		InputActionSetupExtensions.BindingSyntax endIterator;
		return inputAction.ForEachCompositeOfAction(iterator, action, out endIterator);
	}
```

- `public static ForEachCompositeOfAction(UnityEngine.InputSystem.InputAction inputAction, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action) : System.Boolean`  

```csharp
public static bool ForEachCompositeOfAction(this InputAction inputAction, Func<InputActionSetupExtensions.BindingSyntax, bool> action)
	{
		if (action == null)
		{
			return false;
		}
		if (!inputAction.TryGetFirstCompositeOfAction(out var iterator))
		{
			return false;
		}
		InputActionSetupExtensions.BindingSyntax endIterator;
		return inputAction.ForEachCompositeOfAction(iterator, action, out endIterator);
	}
```

- `public static ForEachPartOfCompositeWithName(UnityEngine.InputSystem.InputAction inputAction, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax startIterator, System.String partName, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& endIterator) : System.Boolean`  

```csharp
public static bool ForEachPartOfCompositeWithName(this InputAction inputAction, string partName, Func<InputActionSetupExtensions.BindingSyntax, bool> action)
	{
		if (action == null)
		{
			return false;
		}
		if (!inputAction.TryGetFirstCompositeOfAction(out var iterator))
		{
			return false;
		}
		InputActionSetupExtensions.BindingSyntax endIterator;
		return inputAction.ForEachPartOfCompositeWithName(iterator, partName, action, out endIterator);
	}
```

- `public static ForEachPartOfCompositeWithName(UnityEngine.InputSystem.InputAction inputAction, System.String partName, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action) : System.Boolean`  

```csharp
public static bool ForEachPartOfCompositeWithName(this InputAction inputAction, string partName, Func<InputActionSetupExtensions.BindingSyntax, bool> action)
	{
		if (action == null)
		{
			return false;
		}
		if (!inputAction.TryGetFirstCompositeOfAction(out var iterator))
		{
			return false;
		}
		InputActionSetupExtensions.BindingSyntax endIterator;
		return inputAction.ForEachPartOfCompositeWithName(iterator, partName, action, out endIterator);
	}
```

- `public static TryGetCompositeOfActionWithName(UnityEngine.InputSystem.InputAction action, System.String compositeName, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& iterator) : System.Boolean`  

```csharp
public static bool TryGetCompositeOfActionWithName(this InputAction action, string compositeName, out InputActionSetupExtensions.BindingSyntax iterator)
	{
		iterator = new InputActionSetupExtensions.BindingSyntax(action.actionMap, -1, action).NextCompositeBinding();
		while (iterator.valid && !iterator.binding.TriggersAction(action))
		{
			iterator = iterator.NextCompositeBinding();
		}
		while (iterator.valid && iterator.binding.TriggersAction(action) && iterator.binding.name != compositeName)
		{
			iterator = iterator.NextCompositeBinding();
		}
		if (iterator.valid)
		{
			return iterator.binding.TriggersAction(action);
		}
		return false;
	}
```

- `public static TryGetFirstCompositeOfAction(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& iterator) : System.Boolean`  

```csharp
public static bool TryGetFirstCompositeOfAction(this InputAction action, out InputActionSetupExtensions.BindingSyntax iterator)
	{
		iterator = new InputActionSetupExtensions.BindingSyntax(action.actionMap, -1, action).NextCompositeBinding();
		while (iterator.valid && !iterator.binding.TriggersAction(action))
		{
			iterator = iterator.NextCompositeBinding();
		}
		if (iterator.valid)
		{
			return iterator.binding.TriggersAction(action);
		}
		return false;
	}
```


