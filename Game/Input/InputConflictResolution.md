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
public void Dispose()
	{
		InputManager.instance.EventActionsChanged -= OnActionsChanged;
		InputManager.instance.EventPreResolvedActionChanged -= OnPreResolvedActionChanged;
		InputManager.instance.EventControlSchemeChanged -= OnControlSchemeChanged;
	}
```

- `public Initialize() : System.Void`  

```csharp
public void Initialize()
	{
		InputManager.instance.EventActionsChanged += OnActionsChanged;
		InputManager.instance.EventPreResolvedActionChanged += OnPreResolvedActionChanged;
		InputManager.instance.EventControlSchemeChanged += OnControlSchemeChanged;
	}
```

- `private OnActionsChanged() : System.Void`  

```csharp
private void OnActionsChanged()
	{
		if (!m_UpdateInProgress)
		{
			m_ActionsDirty = true;
			m_ConflictsDirty = true;
		}
	}
```

- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme) : System.Void`  

```csharp
private void OnControlSchemeChanged(InputManager.ControlScheme scheme)
	{
		if (!m_UpdateInProgress)
		{
			m_ConflictsDirty = true;
		}
	}
```

- `private OnPreResolvedActionChanged() : System.Void`  

```csharp
private void OnPreResolvedActionChanged()
	{
		if (!m_UpdateInProgress)
		{
			m_ConflictsDirty = true;
		}
	}
```

- `private RefreshActions() : System.Void`  

```csharp
private void RefreshActions()
	{
		m_SystemActions.Clear();
		m_UIActions.Clear();
		m_ModActions.Clear();
		foreach (ProxyAction action in InputManager.instance.actions)
		{
			if (!action.isBuiltIn)
			{
				m_ModActions.Add(new State(action));
			}
			else if (action.isSystemAction)
			{
				m_SystemActions.Add(new State(action));
			}
			else
			{
				m_UIActions.Add(new State(action));
			}
		}
	}
```

- `private ResolveConflicts() : System.Void`  

```csharp
private void ResolveConflicts()
	{
		foreach (State uIAction in m_UIActions)
		{
			uIAction.Reset();
		}
		foreach (State modAction in m_ModActions)
		{
			modAction.Reset();
		}
		foreach (State systemAction in m_SystemActions)
		{
			if (!systemAction.enabled)
			{
				continue;
			}
			foreach (State uIAction2 in m_UIActions)
			{
				if (uIAction2.enabled)
				{
					Resolve(systemAction, uIAction2);
				}
			}
			foreach (State modAction2 in m_ModActions)
			{
				if (modAction2.enabled)
				{
					Resolve(systemAction, modAction2);
				}
			}
		}
		foreach (State uIAction3 in m_UIActions)
		{
			if (!uIAction3.enabled)
			{
				continue;
			}
			foreach (State modAction3 in m_ModActions)
			{
				if (modAction3.enabled)
				{
					Resolve(uIAction3, modAction3);
				}
			}
		}
		foreach (State uIAction4 in m_UIActions)
		{
			uIAction4.Apply();
		}
		foreach (State modAction4 in m_ModActions)
		{
			modAction4.Apply();
		}
		static void Resolve(State primary, State secondary)
		{
			if (InputManager.HasConflicts(primary.m_Action, secondary.m_Action, primary.m_Action.preResolvedMask, secondary.m_Action.preResolvedMask))
			{
				secondary.m_HasConflict = true;
			}
		}
	}
```

- `public Update() : System.Void`  

```csharp
public void Update()
	{
		m_UpdateInProgress = true;
		if (m_ActionsDirty)
		{
			RefreshActions();
			m_ActionsDirty = false;
			this.EventActionRefreshed?.Invoke();
		}
		if (m_ConflictsDirty)
		{
			ResolveConflicts();
			m_ConflictsDirty = false;
			this.EventConflictResolved?.Invoke();
		}
		m_UpdateInProgress = false;
	}
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

