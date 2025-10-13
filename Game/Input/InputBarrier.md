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
public InputBarrier(System.String barrierName, Game.Input.ProxyActionMap map, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
```

- `public InputBarrier(System.String barrierName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(System.String barrierName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
```

- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
```

- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
```

- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

```csharp
public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask, System.Boolean blocked);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private Update() : System.Void`  

```csharp
private System.Void Update();
```


## Nested types

- `Game.Input.InputBarrier+<>c`  

