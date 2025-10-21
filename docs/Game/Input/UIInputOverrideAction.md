# Game.Input.UIInputOverrideAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.UIBaseInputAction`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class UIInputOverrideAction : Game.Input.UIBaseInputAction
{
    public Game.Input.UIBaseInputAction m_Source;
    public System.Boolean m_OverridePriority;

    public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get; }

    public UIInputOverrideAction();

    private Game.Input.DisplayNameOverride <GetState>b__2_0(System.String source, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform);
    public virtual Game.Input.IProxyAction GetState(System.String source);
    public virtual Game.Input.IProxyAction GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter);
}
```


## Fields

- `public Game.Input.UIBaseInputAction m_Source`  

```csharp
public Game.Input.UIBaseInputAction m_Source;
```

- `public System.Boolean m_OverridePriority`  

```csharp
public System.Boolean m_OverridePriority;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get; }
```


## Constructors

- `public UIInputOverrideAction()`  

```csharp
public UIInputOverrideAction();
```


## Methods

- `private <GetState>b__2_0(System.String source, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform) : Game.Input.DisplayNameOverride`  

```csharp
private Game.Input.DisplayNameOverride <GetState>b__2_0(System.String source, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform);
```

- `public virtual GetState(System.String source) : Game.Input.IProxyAction`  

```csharp
public virtual Game.Input.IProxyAction GetState(System.String source);
```

- `public virtual GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter) : Game.Input.IProxyAction`  

```csharp
public virtual Game.Input.IProxyAction GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter);
```


