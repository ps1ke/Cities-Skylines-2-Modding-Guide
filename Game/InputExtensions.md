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
public static System.Boolean ForEachCompositeOfAction(UnityEngine.InputSystem.InputAction inputAction, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax startIterator, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& endIterator);
```

- `public static ForEachCompositeOfAction(UnityEngine.InputSystem.InputAction inputAction, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action) : System.Boolean`  

```csharp
public static System.Boolean ForEachCompositeOfAction(UnityEngine.InputSystem.InputAction inputAction, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action);
```

- `public static ForEachPartOfCompositeWithName(UnityEngine.InputSystem.InputAction inputAction, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax startIterator, System.String partName, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& endIterator) : System.Boolean`  

```csharp
public static System.Boolean ForEachPartOfCompositeWithName(UnityEngine.InputSystem.InputAction inputAction, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax startIterator, System.String partName, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& endIterator);
```

- `public static ForEachPartOfCompositeWithName(UnityEngine.InputSystem.InputAction inputAction, System.String partName, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action) : System.Boolean`  

```csharp
public static System.Boolean ForEachPartOfCompositeWithName(UnityEngine.InputSystem.InputAction inputAction, System.String partName, System.Func<UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax, System.Boolean> action);
```

- `public static TryGetCompositeOfActionWithName(UnityEngine.InputSystem.InputAction action, System.String compositeName, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& iterator) : System.Boolean`  

```csharp
public static System.Boolean TryGetCompositeOfActionWithName(UnityEngine.InputSystem.InputAction action, System.String compositeName, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& iterator);
```

- `public static TryGetFirstCompositeOfAction(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& iterator) : System.Boolean`  

```csharp
public static System.Boolean TryGetFirstCompositeOfAction(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& iterator);
```


