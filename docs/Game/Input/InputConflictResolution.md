# Game.Input.InputConflictResolution

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.Action EventActionRefreshed`  
- `private System.Action EventConflictResolved`  
- `private System.Boolean m_ActionsDirty`  
- `private System.Boolean m_ConflictsDirty`  
- `private System.Boolean m_UpdateInProgress`  
- `private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_SystemActions`  
- `private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_UIActions`  
- `private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_ModActions`  

## Constructors

- `public InputConflictResolution()`  

## Methods

- `internal static <ResolveConflicts>g__Resolve|19_0(Game.Input.InputConflictResolution+State primary, Game.Input.InputConflictResolution+State secondary) : System.Void`  
- `public Dispose() : System.Void`  
- `public Initialize() : System.Void`  
- `private OnActionsChanged() : System.Void`  
- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme) : System.Void`  
- `private OnPreResolvedActionChanged() : System.Void`  
- `private RefreshActions() : System.Void`  
- `private ResolveConflicts() : System.Void`  
- `public Update() : System.Void`  

## Events

- `EventActionRefreshed` : `System.Action`  
- `EventConflictResolved` : `System.Action`  

## Nested types

- `Game.Input.InputConflictResolution+State`  

