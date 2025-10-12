# Game.Input.UIInputOverrideAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.UIBaseInputAction`  

**Attributes:** `CreateAssetMenu`  

## Fields

- `public Game.Input.UIBaseInputAction m_Source`  
- `public System.Boolean m_OverridePriority`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Input.UIInputActionPart> actionParts { get }`  

## Constructors

- `public UIInputOverrideAction()`  

## Methods

- `private <GetState>b__2_0(System.String source, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform) : Game.Input.DisplayNameOverride`  
- `public virtual GetState(System.String source) : Game.Input.IProxyAction`  
- `public virtual GetState(System.String source, Game.Input.UIBaseInputAction+DisplayGetter displayNameGetter) : Game.Input.IProxyAction`  

