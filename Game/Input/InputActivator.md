# Game.Input.InputActivator

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class InputActivator : System.IDisposable
{
    private readonly Game.Input.ProxyAction[] m_Actions;
    private readonly System.String m_Name;
    private System.Boolean m_Enabled;
    private Game.Input.InputManager+DeviceType m_Mask;
    private System.Boolean m_Disposed;

    public System.String name { get; }
    public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get; }
    public System.Boolean enabled { get; set; }
    public Game.Input.InputManager+DeviceType mask { get; set; }

    public InputActivator(System.String activatorName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, System.Boolean enabled);
    internal InputActivator(System.Boolean ignoreIsBuiltIn, System.String activatorName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, System.Boolean enabled);
    public InputActivator(System.String activatorName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask, System.Boolean enabled);
    internal InputActivator(System.Boolean ignoreIsBuiltIn, System.String activatorName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask, System.Boolean enabled);

    public System.Void Dispose();
    private System.Void Update();
}
```


## Fields

- `private readonly Game.Input.ProxyAction[] m_Actions`  

```csharp
private readonly Game.Input.ProxyAction[] m_Actions;
```

- `private readonly System.String m_Name`  

```csharp
private readonly System.String m_Name;
```

- `private System.Boolean m_Enabled`  

```csharp
private System.Boolean m_Enabled;
```

- `private Game.Input.InputManager+DeviceType m_Mask`  

```csharp
private Game.Input.InputManager+DeviceType m_Mask;
```

- `private System.Boolean m_Disposed`  

```csharp
private System.Boolean m_Disposed;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get; }
```

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public Game.Input.InputManager+DeviceType mask { get; set }`  

```csharp
public Game.Input.InputManager+DeviceType mask { get; set; }
```


## Constructors

- `public InputActivator(System.String activatorName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask = All, System.Boolean enabled = False)`  

```csharp
internal InputActivator(bool ignoreIsBuiltIn, string activatorName, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool enabled = false)
	{
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		if (!ignoreIsBuiltIn && m_Actions.Any((ProxyAction a) => a.isBuiltIn))
		{
			throw new ArgumentException("Activator can not be created for built-in action");
		}
		m_Name = activatorName ?? "InputActivator";
		m_Mask = mask;
		ProxyAction[] array = m_Actions;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Activators.Add(this);
		}
		this.enabled = enabled;
	}
```

- `internal InputActivator(System.Boolean ignoreIsBuiltIn, System.String activatorName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask = All, System.Boolean enabled = False)`  

```csharp
internal InputActivator(bool ignoreIsBuiltIn, string activatorName, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool enabled = false)
	{
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		if (!ignoreIsBuiltIn && m_Actions.Any((ProxyAction a) => a.isBuiltIn))
		{
			throw new ArgumentException("Activator can not be created for built-in action");
		}
		m_Name = activatorName ?? "InputActivator";
		m_Mask = mask;
		ProxyAction[] array = m_Actions;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Activators.Add(this);
		}
		this.enabled = enabled;
	}
```

- `public InputActivator(System.String activatorName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean enabled = False)`  

```csharp
internal InputActivator(bool ignoreIsBuiltIn, string activatorName, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool enabled = false)
	{
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		if (!ignoreIsBuiltIn && m_Actions.Any((ProxyAction a) => a.isBuiltIn))
		{
			throw new ArgumentException("Activator can not be created for built-in action");
		}
		m_Name = activatorName ?? "InputActivator";
		m_Mask = mask;
		ProxyAction[] array = m_Actions;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Activators.Add(this);
		}
		this.enabled = enabled;
	}
```

- `internal InputActivator(System.Boolean ignoreIsBuiltIn, System.String activatorName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean enabled = False)`  

```csharp
internal InputActivator(bool ignoreIsBuiltIn, string activatorName, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool enabled = false)
	{
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		if (!ignoreIsBuiltIn && m_Actions.Any((ProxyAction a) => a.isBuiltIn))
		{
			throw new ArgumentException("Activator can not be created for built-in action");
		}
		m_Name = activatorName ?? "InputActivator";
		m_Mask = mask;
		ProxyAction[] array = m_Actions;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Activators.Add(this);
		}
		this.enabled = enabled;
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		if (!m_Disposed)
		{
			m_Disposed = true;
			ProxyAction[] array = m_Actions;
			foreach (ProxyAction obj in array)
			{
				obj.m_Activators.Remove(this);
				obj.UpdateState();
			}
		}
	}
```

- `private Update() : System.Void`  

```csharp
private void Update()
	{
		ProxyAction[] array = m_Actions;
		for (int i = 0; i < array.Length; i++)
		{
			array[i].UpdateState();
		}
	}
```


## Nested types

- `Game.Input.InputActivator+<>c`  

