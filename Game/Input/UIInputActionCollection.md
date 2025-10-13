# Game.Input.UIInputActionCollection

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class UIInputActionCollection : UnityEngine.ScriptableObject
{
    public Game.Input.UIBaseInputAction[] m_InputActions;

    public UIInputActionCollection();

    public Game.Input.IProxyAction GetActionState(System.String actionName, System.String source);
}
```


## Fields

- `public Game.Input.UIBaseInputAction[] m_InputActions`  

```csharp
public Game.Input.UIBaseInputAction[] m_InputActions;
```


## Constructors

- `public UIInputActionCollection()`  

```csharp
public UIInputActionCollection();
```


## Methods

- `public GetActionState(System.String actionName, System.String source) : Game.Input.IProxyAction`  

```csharp
public Game.Input.IProxyAction GetActionState(System.String actionName, System.String source);
```


## Nested types

- `Game.Input.UIInputActionCollection+<>c__DisplayClass1_0`  

