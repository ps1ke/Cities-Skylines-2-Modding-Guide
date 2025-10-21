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
internal ProxyActionMap(UnityEngine.InputSystem.InputActionMap sourceMap);
```


## Methods

- `public AddAction(Game.Input.ProxyAction+Info actionInfo, System.Boolean bulk = False) : Game.Input.ProxyAction`  

```csharp
public Game.Input.ProxyAction AddAction(Game.Input.ProxyAction+Info actionInfo, System.Boolean bulk);
```

- `public FindAction(System.String name) : Game.Input.ProxyAction`  

```csharp
public Game.Input.ProxyAction FindAction(System.String name);
```

- `internal FindAction(UnityEngine.InputSystem.InputAction action) : Game.Input.ProxyAction`  

```csharp
internal Game.Input.ProxyAction FindAction(UnityEngine.InputSystem.InputAction action);
```

- `internal InitActions() : System.Void`  

```csharp
internal System.Void InitActions();
```

- `public TryFindAction(System.String name, Game.Input.ProxyAction& action) : System.Boolean`  

```csharp
public System.Boolean TryFindAction(System.String name, Game.Input.ProxyAction& action);
```

- `internal UpdateState() : System.Void`  

```csharp
internal System.Void UpdateState();
```


## Nested types

- `Game.Input.ProxyActionMap+<>c`  
- `Game.Input.ProxyActionMap+<>c__DisplayClass25_0`  
- `Game.Input.ProxyActionMap+<get_bindings>d__14`  

