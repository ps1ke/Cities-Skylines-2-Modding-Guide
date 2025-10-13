# Game.Input.UIInputCombinedAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.UIBaseInputAction`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class UIInputCombinedAction : Game.Input.UIBaseInputAction
{
    public Game.Input.UIInputActionPart[] m_Parts;

    public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get; }

    public UIInputCombinedAction();

    public virtual Game.Input.IProxyAction GetState(System.String source);
    public virtual Game.Input.IProxyAction GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter);
}
```


## Fields

- `public Game.Input.UIInputActionPart[] m_Parts`  

```csharp
public Game.Input.UIInputActionPart[] m_Parts;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get; }
```


## Constructors

- `public UIInputCombinedAction()`  

```csharp
public UIInputCombinedAction();
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

- `Game.Input.UIInputCombinedAction+State`  

