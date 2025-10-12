# Game.Input.UIBaseInputAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class abstract public  

**Base:** `UnityEngine.ScriptableObject`  

## Fields

- `public System.String m_AliasName`  
- `public Game.Input.UIBaseInputAction+Priority m_DisplayPriority`  
- `public Game.Input.InputManager+DeviceType m_DisplayMask`  
- `public System.Boolean m_ShowInOptions`  
- `public Game.Input.OptionGroupOverride m_OptionGroupOverride`  

## Properties

- `public System.String aliasName { get }`  
- `public System.Int32 displayPriority { get }`  
- `public System.Boolean showInOptions { get }`  
- `public Game.Input.OptionGroupOverride optionGroupOverride { get }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get }`  

## Constructors

- `protected UIBaseInputAction()`  

## Methods

- `public GetDisplayName(Game.Input.UIInputActionPart actionPart, System.String source) : Game.Input.DisplayNameOverride`  
- `public abstract GetState(System.String source) : Game.Input.IProxyAction`  
- `public abstract GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter) : Game.Input.IProxyAction`  

## Nested types

- `Game.Input.UIBaseInputAction+DisplayGetter`  
- `Game.Input.UIBaseInputAction+IState`  
- `Game.Input.UIBaseInputAction+Priority`  
- `Game.Input.UIBaseInputAction+ProcessAs`  
- `Game.Input.UIBaseInputAction+Transform`  

