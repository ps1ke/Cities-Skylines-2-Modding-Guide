# Game.Input.InputConflictResolution

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class InputConflictResolution : System.IDisposable
{
    private System.Action EventActionRefreshed;
    private System.Action EventConflictResolved;
    private System.Boolean m_ActionsDirty;
    private System.Boolean m_ConflictsDirty;
    private System.Boolean m_UpdateInProgress;
    private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_SystemActions;
    private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_UIActions;
    private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_ModActions;

    public InputConflictResolution();

    internal static System.Void <ResolveConflicts>g__Resolve|19_0(Game.Input.InputConflictResolution+State primary, Game.Input.InputConflictResolution+State secondary);
    public System.Void Dispose();
    public System.Void Initialize();
    private System.Void OnActionsChanged();
    private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme);
    private System.Void OnPreResolvedActionChanged();
    private System.Void RefreshActions();
    private System.Void ResolveConflicts();
    public System.Void Update();
}
```


## Fields

- `private System.Action EventActionRefreshed`  

```csharp
private System.Action EventActionRefreshed;
```

- `private System.Action EventConflictResolved`  

```csharp
private System.Action EventConflictResolved;
```

- `private System.Boolean m_ActionsDirty`  

```csharp
private System.Boolean m_ActionsDirty;
```

- `private System.Boolean m_ConflictsDirty`  

```csharp
private System.Boolean m_ConflictsDirty;
```

- `private System.Boolean m_UpdateInProgress`  

```csharp
private System.Boolean m_UpdateInProgress;
```

- `private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_SystemActions`  

```csharp
private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_SystemActions;
```

- `private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_UIActions`  

```csharp
private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_UIActions;
```

- `private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_ModActions`  

```csharp
private System.Collections.Generic.List<Game.Input.InputConflictResolution+State> m_ModActions;
```


## Constructors

- `public InputConflictResolution()`  

```csharp
public InputConflictResolution();
```


## Methods

- `internal static <ResolveConflicts>g__Resolve|19_0(Game.Input.InputConflictResolution+State primary, Game.Input.InputConflictResolution+State secondary) : System.Void`  

```csharp
internal static System.Void <ResolveConflicts>g__Resolve|19_0(Game.Input.InputConflictResolution+State primary, Game.Input.InputConflictResolution+State secondary);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Initialize() : System.Void`  

```csharp
public System.Void Initialize();
```

- `private OnActionsChanged() : System.Void`  

```csharp
private System.Void OnActionsChanged();
```

- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme) : System.Void`  

```csharp
private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme);
```

- `private OnPreResolvedActionChanged() : System.Void`  

```csharp
private System.Void OnPreResolvedActionChanged();
```

- `private RefreshActions() : System.Void`  

```csharp
private System.Void RefreshActions();
```

- `private ResolveConflicts() : System.Void`  

```csharp
private System.Void ResolveConflicts();
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


## Events

- `EventActionRefreshed` : `System.Action`  

```csharp
public event System.Action EventActionRefreshed;
```

- `EventConflictResolved` : `System.Action`  

```csharp
public event System.Action EventConflictResolved;
```


## Nested types

- `Game.Input.InputConflictResolution+State`  

