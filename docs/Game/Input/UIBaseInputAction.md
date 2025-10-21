# Game.Input.UIBaseInputAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class abstract public  

**Base:** `UnityEngine.ScriptableObject`  

## Code

```csharp
public abstract class UIBaseInputAction : UnityEngine.ScriptableObject
{
    public System.String m_AliasName;
    public Game.Input.UIBaseInputAction+Priority m_DisplayPriority;
    public Game.Input.InputManager+DeviceType m_DisplayMask;
    public System.Boolean m_ShowInOptions;
    public Game.Input.OptionGroupOverride m_OptionGroupOverride;

    public System.String aliasName { get; }
    public System.Int32 displayPriority { get; }
    public System.Boolean showInOptions { get; }
    public Game.Input.OptionGroupOverride optionGroupOverride { get; }
    public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get; }

    protected UIBaseInputAction();

    public Game.Input.DisplayNameOverride GetDisplayName(Game.Input.UIInputActionPart actionPart, System.String source);
    public abstract Game.Input.IProxyAction GetState(System.String source);
    public abstract Game.Input.IProxyAction GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter);
}
```


## Fields

- `public System.String m_AliasName`  

```csharp
public System.String m_AliasName;
```

- `public Game.Input.UIBaseInputAction+Priority m_DisplayPriority`  

```csharp
public Game.Input.UIBaseInputAction+Priority m_DisplayPriority;
```

- `public Game.Input.InputManager+DeviceType m_DisplayMask`  

```csharp
public Game.Input.InputManager+DeviceType m_DisplayMask;
```

- `public System.Boolean m_ShowInOptions`  

```csharp
public System.Boolean m_ShowInOptions;
```

- `public Game.Input.OptionGroupOverride m_OptionGroupOverride`  

```csharp
public Game.Input.OptionGroupOverride m_OptionGroupOverride;
```


## Properties

- `public System.String aliasName { get }`  

```csharp
public System.String aliasName { get; }
```

- `public System.Int32 displayPriority { get }`  

```csharp
public System.Int32 displayPriority { get; }
```

- `public System.Boolean showInOptions { get }`  

```csharp
public System.Boolean showInOptions { get; }
```

- `public Game.Input.OptionGroupOverride optionGroupOverride { get }`  

```csharp
public Game.Input.OptionGroupOverride optionGroupOverride { get; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get; }
```


## Constructors

- `protected UIBaseInputAction()`  

```csharp
protected UIBaseInputAction();
```


## Methods

- `public GetDisplayName(Game.Input.UIInputActionPart actionPart, System.String source) : Game.Input.DisplayNameOverride`  

```csharp
public Game.Input.DisplayNameOverride GetDisplayName(Game.Input.UIInputActionPart actionPart, System.String source);
```

- `public abstract GetState(System.String source) : Game.Input.IProxyAction`  

```csharp
public abstract Game.Input.IProxyAction GetState(System.String source);
```

- `public abstract GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter) : Game.Input.IProxyAction`  

```csharp
public abstract Game.Input.IProxyAction GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter);
```


## Nested types

- `Game.Input.UIBaseInputAction+DisplayGetter`  
- `Game.Input.UIBaseInputAction+IState`  
- `Game.Input.UIBaseInputAction+Priority`  
- `Game.Input.UIBaseInputAction+ProcessAs`  
- `Game.Input.UIBaseInputAction+Transform`  

