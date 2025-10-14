# Game.InputExtensions

**Assembly:** Assembly-CSharp.dll  
**Namespace:** Game

**Type:** public static class

**Base:** System.Object

**Summary:** A collection of extension helpers for UnityEngine.InputSystem.InputAction that simplify locating and iterating over composite bindings and their parts (using InputActionSetupExtensions.BindingSyntax). Intended to make it easier for mod code to find specific composite bindings (by name), enumerate all composites for an action, and enumerate parts of a composite binding reliably.

---

## Fields

- None — This static class declares no instance or static fields.

## Properties

- None — This static class declares no properties.

## Constructors

- None — As a static utility class it exposes no public constructors.

## Methods

- `public static bool TryGetCompositeOfActionWithName(this InputAction action, string compositeName, out InputActionSetupExtensions.BindingSyntax iterator)`  
  Attempts to find the first composite binding for the provided InputAction whose composite name matches compositeName. Returns true and sets iterator to the matching composite BindingSyntax if found. Iterates composite bindings until a composite that triggers the given action and has the requested composite name is found. Returns false if no matching composite is present or if iterator becomes invalid.

- `public static bool TryGetFirstCompositeOfAction(this InputAction action, out InputActionSetupExtensions.BindingSyntax iterator)`  
  Locates the first composite binding that triggers the given action and returns true if found, setting iterator to that composite. Useful as a starting point for further iteration over parts or additional composites. Returns false if none found.

- `public static bool ForEachCompositeOfAction(this InputAction inputAction, InputActionSetupExtensions.BindingSyntax startIterator, Func<InputActionSetupExtensions.BindingSyntax, bool> action, out InputActionSetupExtensions.BindingSyntax endIterator)`  
  Iterates over consecutive composite bindings starting from startIterator (advancing via NextCompositeBinding()), invoking the provided delegate for each composite that triggers the provided inputAction. If the delegate ever returns false iteration stops and the method returns false. endIterator is set to the last composite visited. Returns false if the provided delegate is null.

- `public static bool ForEachCompositeOfAction(this InputAction inputAction, Func<InputActionSetupExtensions.BindingSyntax, bool> action)`  
  Convenience overload that starts from the first composite that triggers the action (uses TryGetFirstCompositeOfAction) and invokes the delegate for each composite found. Returns false if action is null or no composite exists.

- `public static bool ForEachPartOfCompositeWithName(this InputAction inputAction, InputActionSetupExtensions.BindingSyntax startIterator, string partName, Func<InputActionSetupExtensions.BindingSyntax, bool> action, out InputActionSetupExtensions.BindingSyntax endIterator)`  
  Iterates parts of a composite binding matching partName, starting from startIterator. If startIterator is currently pointing at a composite, it advances to the first matching part via NextPartBinding(partName). Continues iterating while bindings are part of a composite, trigger the action, and are valid. Calls the delegate for each matching part; if the delegate returns false iteration stops and the method returns false. Returns false for null/empty partName or null delegate.

- `public static bool ForEachPartOfCompositeWithName(this InputAction inputAction, string partName, Func<InputActionSetupExtensions.BindingSyntax, bool> action)`  
  Convenience overload that finds the first composite for the action and then iterates over parts with the given partName, invoking the delegate for each part. Returns false if action is null or if no composite exists.

Example usage notes:
- These helpers rely on InputActionSetupExtensions.BindingSyntax traversal methods such as NextCompositeBinding() and NextPartBinding(string), and on BindingSyntax.binding properties like isComposite, isPartOfComposite and TriggersAction(InputAction).
- All iteration methods return false if a supplied delegate is null.
- Typical pattern: call TryGetFirstCompositeOfAction to get a start iterator, then call ForEachPartOfCompositeWithName to process every named part.

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