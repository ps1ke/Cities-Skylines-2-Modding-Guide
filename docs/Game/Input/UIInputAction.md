# Game.Input.UIInputAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.UIBaseInputAction`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class UIInputAction : Game.Input.UIBaseInputAction
{
    public UnityEngine.InputSystem.InputActionReference m_Action;
    public Game.Input.UIBaseInputAction+ProcessAs m_ProcessAs;
    public Game.Input.UIBaseInputAction+Transform m_Transform;
    public Game.Input.InputManager+DeviceType m_Mask;
    private Game.Input.UIInputActionPart[] m_ActionParts;

    public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get; }

    public UIInputAction();

    public virtual Game.Input.IProxyAction GetState(System.String source);
    public virtual Game.Input.IProxyAction GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter);
}
```


## Fields

- `public UnityEngine.InputSystem.InputActionReference m_Action`  

```csharp
public UnityEngine.InputSystem.InputActionReference m_Action;
```

- `public Game.Input.UIBaseInputAction+ProcessAs m_ProcessAs`  

```csharp
public Game.Input.UIBaseInputAction+ProcessAs m_ProcessAs;
```

- `public Game.Input.UIBaseInputAction+Transform m_Transform`  

```csharp
public Game.Input.UIBaseInputAction+Transform m_Transform;
```

- `public Game.Input.InputManager+DeviceType m_Mask`  

```csharp
public Game.Input.InputManager+DeviceType m_Mask;
```

- `private Game.Input.UIInputActionPart[] m_ActionParts`  

```csharp
private Game.Input.UIInputActionPart[] m_ActionParts;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get; }
```


## Constructors

- `public UIInputAction()`  

```csharp
public UIInputAction();
```


## Methods

- `public virtual GetState(System.String source) : Game.Input.IProxyAction`  

```csharp
public virtual Game.Input.IProxyAction GetState(System.String source);
```

- `public virtual GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter) : Game.Input.IProxyAction`  

```csharp
public virtual Game.Input.IProxyAction GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter);
```


## Nested types

- `Game.Input.UIInputAction+State`  

