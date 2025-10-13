# Game.UI.InputActionBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class InputActionBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private Colossal.UI.Binding.RawEventBinding m_ActionPerformedBinding;
    private Colossal.UI.Binding.RawEventBinding m_ActionReleasedBinding;
    private Colossal.UI.Binding.EventBinding m_ActionRefreshedBinding;
    private readonly System.Collections.Generic.List<Game.UI.InputActionBindings+ActionState> m_UIActionStates;
    private readonly System.Collections.Generic.Dictionary<System.ValueTuple<Game.Input.ProxyAction, Game.Input.UIBaseInputAction+ProcessAs>, Game.UI.InputActionBindings+IEventTrigger> m_Triggers;
    private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> m_ActionOrder;
    private System.Boolean m_ActionsDirty;
    private System.Boolean m_ConflictsDirty;
    private System.Boolean m_UpdateInProgress;
    private static const System.Int32 kDisabledPriority;
    private static const System.String kGroup;

    public InputActionBindings();

    public System.Void Dispose();
    private System.Void OnActionsChanged();
    private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme);
    private System.Void RefreshActions();
    private System.Void ResolveConflicts();
    private System.Void SetActionPriority(System.String action, System.Int32 priority);
    private System.Void SetConflictsDirty();
    public virtual System.Boolean Update();
}
```


## Fields

- `private Colossal.UI.Binding.RawEventBinding m_ActionPerformedBinding`  

```csharp
private Colossal.UI.Binding.RawEventBinding m_ActionPerformedBinding;
```

- `private Colossal.UI.Binding.RawEventBinding m_ActionReleasedBinding`  

```csharp
private Colossal.UI.Binding.RawEventBinding m_ActionReleasedBinding;
```

- `private Colossal.UI.Binding.EventBinding m_ActionRefreshedBinding`  

```csharp
private Colossal.UI.Binding.EventBinding m_ActionRefreshedBinding;
```

- `private readonly System.Collections.Generic.List<Game.UI.InputActionBindings+ActionState> m_UIActionStates`  

```csharp
private readonly System.Collections.Generic.List<Game.UI.InputActionBindings+ActionState> m_UIActionStates;
```

- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<Game.Input.ProxyAction, Game.Input.UIBaseInputAction+ProcessAs>, Game.UI.InputActionBindings+IEventTrigger> m_Triggers`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.ValueTuple<Game.Input.ProxyAction, Game.Input.UIBaseInputAction+ProcessAs>, Game.UI.InputActionBindings+IEventTrigger> m_Triggers;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> m_ActionOrder`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> m_ActionOrder;
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

- `private static const System.Int32 kDisabledPriority`  

```csharp
private static const System.Int32 kDisabledPriority;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public InputActionBindings()`  

```csharp
public InputActionBindings()
	{
		AddBinding(m_ActionPerformedBinding = new RawEventBinding("input", "onActionPerformed"));
		AddBinding(m_ActionReleasedBinding = new RawEventBinding("input", "onActionReleased"));
		AddBinding(new TriggerBinding<string, int>("input", "setActionPriority", SetActionPriority));
		string[] initialValue = Game.Input.InputManager.instance.uiActionCollection.m_InputActions.Select((UIBaseInputAction a) => a.aliasName).ToArray();
		AddBinding(new ValueBinding<string[]>("input", "actionNames", initialValue, new ArrayWriter<string>()));
		AddBinding(m_ActionRefreshedBinding = new EventBinding("input", "onActionsRefreshed"));
		Game.Input.InputManager.instance.EventActionsChanged += OnActionsChanged;
		Game.Input.InputManager.instance.EventControlSchemeChanged += OnControlSchemeChanged;
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		Game.Input.InputManager.instance.EventActionsChanged -= OnActionsChanged;
		Game.Input.InputManager.instance.EventControlSchemeChanged -= OnControlSchemeChanged;
		foreach (ActionState uIActionState in m_UIActionStates)
		{
			uIActionState.Dispose();
		}
		foreach (IEventTrigger value in m_Triggers.Values)
		{
			value.Dispose();
		}
		m_Triggers.Clear();
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
private void OnControlSchemeChanged(Game.Input.InputManager.ControlScheme scheme)
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
		for (int i = 0; i < m_UIActionStates.Count; i++)
		{
			m_UIActionStates[i].Dispose();
			if (m_Triggers.TryGetValue((m_UIActionStates[i].action, m_UIActionStates[i].processAs), out var value))
			{
				value.states.Remove(m_UIActionStates[i]);
				if (value.states.Count == 0)
				{
					value.Dispose();
					m_Triggers.Remove((m_UIActionStates[i].action, m_UIActionStates[i].processAs));
				}
			}
		}
		m_UIActionStates.Clear();
		m_ActionOrder.Clear();
		for (int j = 0; j < Game.Input.InputManager.instance.uiActionCollection.m_InputActions.Length; j++)
		{
			UIBaseInputAction uIBaseInputAction = Game.Input.InputManager.instance.uiActionCollection.m_InputActions[j];
			int count = m_UIActionStates.Count;
			for (int k = 0; k < uIBaseInputAction.actionParts.Count; k++)
			{
				UIInputActionPart uIInputActionPart = uIBaseInputAction.actionParts[k];
				ProxyAction proxyAction = uIInputActionPart.GetProxyAction();
				if (proxyAction.isSet)
				{
					DisplayNameOverride displayName = uIBaseInputAction.GetDisplayName(uIInputActionPart, "InputActionBindings");
					ActionState actionState = new ActionState(proxyAction, uIBaseInputAction.aliasName, displayName, uIInputActionPart.m_ProcessAs, uIInputActionPart.m_Transform, uIInputActionPart.m_Mask);
					actionState.onChanged += SetConflictsDirty;
					if (!m_Triggers.TryGetValue((actionState.action, actionState.processAs), out var value2))
					{
						value2 = IEventTrigger.GetTrigger(this, actionState.action, actionState.processAs);
						m_Triggers.Add((actionState.action, actionState.processAs), value2);
					}
					value2.states.Add(actionState);
					m_UIActionStates.Add(actionState);
				}
			}
			if (count != m_UIActionStates.Count)
			{
				m_ActionOrder[uIBaseInputAction.aliasName] = count;
			}
		}
	}
```

- `private ResolveConflicts() : System.Void`  

```csharp
private void ResolveConflicts()
	{
		ActionState[] array = m_UIActionStates.OrderBy((ActionState a) => a).ToArray();
		Game.Input.InputManager.DeviceType mask = Game.Input.InputManager.instance.mask;
		for (int num = 0; num < m_UIActionStates.Count; num++)
		{
			m_UIActionStates[num].UpdateState();
		}
		for (int num2 = 0; num2 < array.Length; num2++)
		{
			ActionState actionState = array[num2];
			if (actionState.state != ActionState.State.Enabled)
			{
				continue;
			}
			for (int num3 = num2 + 1; num3 < array.Length; num3++)
			{
				ActionState actionState2 = array[num3];
				if (actionState2.state != ActionState.State.Enabled)
				{
					continue;
				}
				if (actionState2.action == actionState.action)
				{
					if (actionState2.transform == actionState.transform || (actionState2.transform & actionState.transform) != UIBaseInputAction.Transform.None)
					{
						actionState2.state = ActionState.State.DisabledDuplicate;
					}
				}
				else if (Game.Input.InputManager.HasConflicts(actionState2.action, actionState.action, actionState.mask & mask, actionState2.mask & mask))
				{
					actionState2.state = ActionState.State.DisabledConflict;
				}
			}
		}
		using (ProxyAction.DeferStateUpdating())
		{
			for (int num4 = 0; num4 < m_UIActionStates.Count; num4++)
			{
				m_UIActionStates[num4].Apply();
			}
		}
	}
```

- `private SetActionPriority(System.String action, System.Int32 priority) : System.Void`  

```csharp
private void SetActionPriority(string action, int priority)
	{
		if (m_ActionOrder.TryGetValue(action, out var i))
		{
			for (; i < m_UIActionStates.Count && m_UIActionStates[i].name == action; i++)
			{
				m_UIActionStates[i].priority = priority;
			}
		}
	}
```

- `private SetConflictsDirty() : System.Void`  

```csharp
private void SetConflictsDirty()
	{
		if (!m_UpdateInProgress)
		{
			m_ConflictsDirty = true;
		}
	}
```

- `public virtual Update() : System.Boolean`  

```csharp
public override bool Update()
	{
		m_UpdateInProgress = true;
		if (m_ActionsDirty)
		{
			RefreshActions();
			m_ActionsDirty = false;
			m_ActionRefreshedBinding.Trigger();
		}
		if (m_ConflictsDirty)
		{
			ResolveConflicts();
			m_ConflictsDirty = false;
		}
		m_UpdateInProgress = false;
		return base.Update();
	}
```


## Nested types

- `Game.UI.InputActionBindings+ActionState`  
- `Game.UI.InputActionBindings+IEventTrigger`  
- `Game.UI.InputActionBindings+EventTrigger<TRawValue, TValue>`  
- `Game.UI.InputActionBindings+DefaultEventTrigger`  
- `Game.UI.InputActionBindings+ButtonEventTrigger`  
- `Game.UI.InputActionBindings+AxisEventTrigger`  
- `Game.UI.InputActionBindings+Vector2EventTrigger`  
- `Game.UI.InputActionBindings+AxisToButtonEventTrigger`  
- `Game.UI.InputActionBindings+Vector2ToButtonEventTrigger`  
- `Game.UI.InputActionBindings+ButtonToAxisEventTrigger`  
- `Game.UI.InputActionBindings+Vector2ToAxisEventTrigger`  
- `Game.UI.InputActionBindings+ButtonToVector2EventTrigger`  
- `Game.UI.InputActionBindings+AxisToVector2EventTrigger`  
- `Game.UI.InputActionBindings+<>c`  

