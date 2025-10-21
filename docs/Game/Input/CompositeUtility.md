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
public static System.Boolean CheckModifiers(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Boolean allowModifiers, System.Int32 modifier);
```

- `public static GetActionType(Game.Input.ActionComponent component) : Game.Input.ActionType`  

```csharp
public static Game.Input.ActionType GetActionType(Game.Input.ActionComponent component);
```

- `public static GetCompositeTypeName(Game.Input.ActionType actionType) : System.String`  

```csharp
public static System.String GetCompositeTypeName(Game.Input.ActionType actionType);
```

- `public static GetCompositeTypeName(System.Type type) : System.String`  

```csharp
public static System.String GetCompositeTypeName(System.Type type);
```

- `public static GetExpectedControlLayout(Game.Input.ActionType actionType) : System.String`  

```csharp
public static System.String GetExpectedControlLayout(Game.Input.ActionType actionType);
```

- `public static GetGuid(System.Int64 part1, System.Int64 part2) : System.Guid`  

```csharp
public static System.Guid GetGuid(System.Int64 part1, System.Int64 part2);
```

- `public static GetInputActionType(Game.Input.ActionType actionType) : UnityEngine.InputSystem.InputActionType`  

```csharp
public static UnityEngine.InputSystem.InputActionType GetInputActionType(Game.Input.ActionType actionType);
```

- `public static ReadValue<T>(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier, System.Collections.Generic.IComparer<T> comparer) : T`  

```csharp
public static T ReadValue<T>(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier, System.Collections.Generic.IComparer<T> comparer);
```

- `public static ReadValueAsButton(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier) : System.Boolean`  

```csharp
public static System.Boolean ReadValueAsButton(UnityEngine.InputSystem.InputBindingCompositeContext& context, System.Int32 button, System.Boolean allowModifiers, System.Int32 modifier);
```

- `public static SetGuid(System.Guid guid, System.Int64& part1, System.Int64& part2) : System.Void`  

```csharp
public static System.Void SetGuid(System.Guid guid, System.Int64& part1, System.Int64& part2);
```


