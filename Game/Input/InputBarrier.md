# Game.Input.InputBarrier

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class InputBarrier : System.IDisposable
{
    private readonly Game.Input.ProxyActionMap[] m_Maps;
    private readonly Game.Input.ProxyAction[] m_Actions;
    private readonly System.String m_Name;
    private System.Boolean m_Blocked;
    private Game.Input.InputManager+DeviceType m_Mask;
    private System.Boolean m_Disposed;

    public System.String name { get; }
    public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyActionMap> maps { get; }
    public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get; }
    public System.Boolean blocked { get; set; }
    public Game.Input.InputManager+DeviceType mask { get; set; }

    public InputBarrier(System.String barrierName, Game.Input.ProxyActionMap map, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
    public InputBarrier(System.String barrierName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
    public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
    public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
    public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);

    public System.Void Dispose();
    private System.Void Update();
}
```


## Fields

- `private readonly Game.Input.ProxyActionMap[] m_Maps`  

```csharp
private readonly Game.Input.ProxyActionMap[] m_Maps;
```

- `private readonly Game.Input.ProxyAction[] m_Actions`  

```csharp
private readonly Game.Input.ProxyAction[] m_Actions;
```

- `private readonly System.String m_Name`  

```csharp
private readonly System.String m_Name;
```

- `private System.Boolean m_Blocked`  

```csharp
private System.Boolean m_Blocked;
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

- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyActionMap> maps { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyActionMap> maps { get; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get; }
```

- `public System.Boolean blocked { get; set }`  

```csharp
public System.Boolean blocked { get; set; }
```

- `public Game.Input.InputManager+DeviceType mask { get; set }`  

```csharp
public Game.Input.InputManager+DeviceType mask { get; set; }
```


## Constructors

- `public InputBarrier(System.String barrierName, Game.Input.ProxyActionMap map, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(string barrierName, IList<ProxyActionMap> maps, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool blocked = false)
	{
		if (maps == null)
		{
			throw new ArgumentNullException("maps");
		}
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Name = barrierName ?? "InputBarrier";
		m_Maps = maps.Where((ProxyActionMap m) => m != null).Distinct().ToArray();
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		m_Mask = mask;
		ProxyActionMap[] array = m_Maps;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Barriers.Add(this);
		}
		ProxyAction[] array2 = m_Actions;
		for (int num = 0; num < array2.Length; num++)
		{
			array2[num].m_Barriers.Add(this);
		}
		this.blocked = blocked;
	}
```

- `public InputBarrier(System.String barrierName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(string barrierName, IList<ProxyActionMap> maps, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool blocked = false)
	{
		if (maps == null)
		{
			throw new ArgumentNullException("maps");
		}
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Name = barrierName ?? "InputBarrier";
		m_Maps = maps.Where((ProxyActionMap m) => m != null).Distinct().ToArray();
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		m_Mask = mask;
		ProxyActionMap[] array = m_Maps;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Barriers.Add(this);
		}
		ProxyAction[] array2 = m_Actions;
		for (int num = 0; num < array2.Length; num++)
		{
			array2[num].m_Barriers.Add(this);
		}
		this.blocked = blocked;
	}
```

- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(string barrierName, IList<ProxyActionMap> maps, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool blocked = false)
	{
		if (maps == null)
		{
			throw new ArgumentNullException("maps");
		}
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Name = barrierName ?? "InputBarrier";
		m_Maps = maps.Where((ProxyActionMap m) => m != null).Distinct().ToArray();
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		m_Mask = mask;
		ProxyActionMap[] array = m_Maps;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Barriers.Add(this);
		}
		ProxyAction[] array2 = m_Actions;
		for (int num = 0; num < array2.Length; num++)
		{
			array2[num].m_Barriers.Add(this);
		}
		this.blocked = blocked;
	}
```

- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(string barrierName, IList<ProxyActionMap> maps, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool blocked = false)
	{
		if (maps == null)
		{
			throw new ArgumentNullException("maps");
		}
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Name = barrierName ?? "InputBarrier";
		m_Maps = maps.Where((ProxyActionMap m) => m != null).Distinct().ToArray();
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		m_Mask = mask;
		ProxyActionMap[] array = m_Maps;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Barriers.Add(this);
		}
		ProxyAction[] array2 = m_Actions;
		for (int num = 0; num < array2.Length; num++)
		{
			array2[num].m_Barriers.Add(this);
		}
		this.blocked = blocked;
	}
```

- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(string barrierName, IList<ProxyActionMap> maps, IList<ProxyAction> actions, InputManager.DeviceType mask = InputManager.DeviceType.All, bool blocked = false)
	{
		if (maps == null)
		{
			throw new ArgumentNullException("maps");
		}
		if (actions == null)
		{
			throw new ArgumentNullException("actions");
		}
		m_Name = barrierName ?? "InputBarrier";
		m_Maps = maps.Where((ProxyActionMap m) => m != null).Distinct().ToArray();
		m_Actions = actions.Where((ProxyAction a) => a != null).Distinct().ToArray();
		m_Mask = mask;
		ProxyActionMap[] array = m_Maps;
		for (int num = 0; num < array.Length; num++)
		{
			array[num].m_Barriers.Add(this);
		}
		ProxyAction[] array2 = m_Actions;
		for (int num = 0; num < array2.Length; num++)
		{
			array2[num].m_Barriers.Add(this);
		}
		this.blocked = blocked;
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
			ProxyActionMap[] array = m_Maps;
			foreach (ProxyActionMap obj in array)
			{
				obj.m_Barriers.Remove(this);
				obj.UpdateState();
			}
			ProxyAction[] array2 = m_Actions;
			foreach (ProxyAction obj2 in array2)
			{
				obj2.m_Barriers.Remove(this);
				obj2.UpdateState();
			}
		}
	}
```

- `private Update() : System.Void`  

```csharp
private void Update()
	{
		ProxyActionMap[] array = m_Maps;
		for (int i = 0; i < array.Length; i++)
		{
			array[i].UpdateState();
		}
		ProxyAction[] array2 = m_Actions;
		for (int i = 0; i < array2.Length; i++)
		{
			array2[i].UpdateState();
		}
	}
```


## Nested types

- `Game.Input.InputBarrier+<>c`  

