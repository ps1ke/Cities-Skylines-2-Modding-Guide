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
public override IProxyAction GetState(string source, DisplayGetter displayNameGetter)
	{
		if (m_Parts.Length == 1)
		{
			ProxyAction proxyAction = m_Parts[0].GetProxyAction();
			DisplayNameOverride displayName = displayNameGetter(source, proxyAction, m_Parts[0].m_Mask, m_Parts[0].m_Transform);
			return new UIInputAction.State(source, proxyAction, displayName, m_Parts[0].m_Mask);
		}
		UIInputAction.State[] array = new UIInputAction.State[m_Parts.Length];
		for (int i = 0; i < m_Parts.Length; i++)
		{
			ProxyAction proxyAction2 = m_Parts[i].GetProxyAction();
			DisplayNameOverride displayName2 = displayNameGetter(source, proxyAction2, m_Parts[0].m_Mask, m_Parts[i].m_Transform);
			array[i] = new UIInputAction.State(source, proxyAction2, displayName2, m_Parts[i].m_Mask);
		}
		return new State(array);
	}
```

- `public virtual GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter) : Game.Input.IProxyAction`  

```csharp
public override IProxyAction GetState(string source, DisplayGetter displayNameGetter)
	{
		if (m_Parts.Length == 1)
		{
			ProxyAction proxyAction = m_Parts[0].GetProxyAction();
			DisplayNameOverride displayName = displayNameGetter(source, proxyAction, m_Parts[0].m_Mask, m_Parts[0].m_Transform);
			return new UIInputAction.State(source, proxyAction, displayName, m_Parts[0].m_Mask);
		}
		UIInputAction.State[] array = new UIInputAction.State[m_Parts.Length];
		for (int i = 0; i < m_Parts.Length; i++)
		{
			ProxyAction proxyAction2 = m_Parts[i].GetProxyAction();
			DisplayNameOverride displayName2 = displayNameGetter(source, proxyAction2, m_Parts[0].m_Mask, m_Parts[i].m_Transform);
			array[i] = new UIInputAction.State(source, proxyAction2, displayName2, m_Parts[i].m_Mask);
		}
		return new State(array);
	}
```


## Nested types

- `Game.Input.UIInputCombinedAction+State`  

