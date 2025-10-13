# Game.Input.ProxyActionMap

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public class ProxyActionMap
{
    private readonly UnityEngine.InputSystem.InputActionMap m_SourceMap;
    private readonly System.Collections.Generic.Dictionary<System.String, Game.Input.ProxyAction> m_Actions;
    internal System.Collections.Generic.HashSet<Game.Input.InputBarrier> m_Barriers;
    private System.Boolean m_Enabled;
    private Game.Input.InputManager+DeviceType m_Mask;

    internal UnityEngine.InputSystem.InputActionMap sourceMap { internal get; }
    public System.String name { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, Game.Input.ProxyAction> actions { get; }
    internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputBarrier> barriers { internal get; }
    public System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> bindings { get; }
    public System.Boolean enabled { get; }
    public Game.Input.InputManager+DeviceType mask { get; internal set; }

    internal ProxyActionMap(UnityEngine.InputSystem.InputActionMap sourceMap);

    public Game.Input.ProxyAction AddAction(Game.Input.ProxyAction+Info actionInfo, System.Boolean bulk);
    public Game.Input.ProxyAction FindAction(System.String name);
    internal Game.Input.ProxyAction FindAction(UnityEngine.InputSystem.InputAction action);
    internal System.Void InitActions();
    public System.Boolean TryFindAction(System.String name, Game.Input.ProxyAction& action);
    internal System.Void UpdateState();
}
```


## Fields

- `private readonly UnityEngine.InputSystem.InputActionMap m_SourceMap`  

```csharp
private readonly UnityEngine.InputSystem.InputActionMap m_SourceMap;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Game.Input.ProxyAction> m_Actions`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Game.Input.ProxyAction> m_Actions;
```

- `internal System.Collections.Generic.HashSet<Game.Input.InputBarrier> m_Barriers`  

```csharp
internal System.Collections.Generic.HashSet<Game.Input.InputBarrier> m_Barriers;
```

- `private System.Boolean m_Enabled`  

```csharp
private System.Boolean m_Enabled;
```

- `private Game.Input.InputManager+DeviceType m_Mask`  

```csharp
private Game.Input.InputManager+DeviceType m_Mask;
```


## Properties

- `internal UnityEngine.InputSystem.InputActionMap sourceMap { internal get }`  

```csharp
internal UnityEngine.InputSystem.InputActionMap sourceMap { internal get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Game.Input.ProxyAction> actions { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, Game.Input.ProxyAction> actions { get; }
```

- `internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputBarrier> barriers { internal get }`  

```csharp
internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputBarrier> barriers { internal get; }
```

- `public System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> bindings { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> bindings { get; }
```

- `public System.Boolean enabled { get }`  

```csharp
public System.Boolean enabled { get; }
```

- `public Game.Input.InputManager+DeviceType mask { get; internal set }`  

```csharp
public Game.Input.InputManager+DeviceType mask { get; internal set; }
```


## Constructors

- `internal ProxyActionMap(UnityEngine.InputSystem.InputActionMap sourceMap)`  

```csharp
internal ProxyActionMap(InputActionMap sourceMap)
	{
		m_SourceMap = sourceMap;
	}
```


## Methods

- `public AddAction(Game.Input.ProxyAction+Info actionInfo, System.Boolean bulk = False) : Game.Input.ProxyAction`  

```csharp
public ProxyAction AddAction(ProxyAction.Info actionInfo, bool bulk = false)
	{
		using (Colossal.PerformanceCounter.Start(delegate(TimeSpan t)
		{
			InputManager.log.InfoFormat("Action \"{1}\" added in {0}ms", t.TotalMilliseconds, actionInfo.m_Name);
		}))
		{
			using (InputManager.DeferUpdating())
			{
				if (TryFindAction(actionInfo.m_Name, out var action))
				{
					return action;
				}
				InputAction inputAction = m_SourceMap.AddAction(actionInfo.m_Name, actionInfo.m_Type.GetInputActionType(), null, null, null, null, actionInfo.m_Type.GetExpectedControlLayout());
				foreach (ProxyComposite.Info composite in actionInfo.m_Composites)
				{
					InputManager.instance.CreateCompositeBinding(inputAction, composite);
				}
				action = new ProxyAction(this, inputAction);
				m_Actions.Add(action.name, action);
				InputManager.instance.InitializeMasks(action);
				return action;
			}
		}
	}
```

- `public FindAction(System.String name) : Game.Input.ProxyAction`  

```csharp
internal ProxyAction FindAction(InputAction action)
	{
		return FindAction(action.name);
	}
```

- `internal FindAction(UnityEngine.InputSystem.InputAction action) : Game.Input.ProxyAction`  

```csharp
internal ProxyAction FindAction(InputAction action)
	{
		return FindAction(action.name);
	}
```

- `internal InitActions() : System.Void`  

```csharp
internal void InitActions()
	{
		foreach (InputAction action in sourceMap.actions)
		{
			ProxyAction proxyAction = new ProxyAction(this, action);
			m_Actions.Add(proxyAction.name, proxyAction);
		}
		UpdateState();
	}
```

- `public TryFindAction(System.String name, Game.Input.ProxyAction& action) : System.Boolean`  

```csharp
public bool TryFindAction(string name, out ProxyAction action)
	{
		return m_Actions.TryGetValue(name, out action);
	}
```

- `internal UpdateState() : System.Void`  

```csharp
internal void UpdateState()
	{
		bool flag = m_Barriers.All((InputBarrier b) => !b.blocked);
		if (flag == m_Enabled)
		{
			return;
		}
		m_Enabled = flag;
		foreach (KeyValuePair<string, ProxyAction> action in m_Actions)
		{
			action.Deconstruct(out var _, out var value);
			value.UpdateState();
		}
	}
```


## Nested types

- `Game.Input.ProxyActionMap+<>c`  
- `Game.Input.ProxyActionMap+<>c__DisplayClass25_0`  
- `Game.Input.ProxyActionMap+<get_bindings>d__14`  

