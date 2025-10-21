# Game.Input.ProxyBinding+Watcher

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class Watcher : System.IDisposable
{
    private System.Boolean m_Disposed;
    private Game.Input.ProxyBinding m_Binding;
    private readonly Game.Input.ProxyAction m_Action;
    private readonly System.Action<Game.Input.ProxyBinding> m_OnChange;
    private static readonly Game.Input.ProxyBinding+Comparer comparer;

    public Game.Input.ProxyBinding binding { get; }
    public System.Boolean isValid { get; }

    public Watcher(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onChange);

    public System.Void Dispose();
    private System.Void OnChanged(Game.Input.ProxyAction action);
}
```


## Fields

- `private System.Boolean m_Disposed`  

```csharp
private System.Boolean m_Disposed;
```

- `private Game.Input.ProxyBinding m_Binding`  

```csharp
private Game.Input.ProxyBinding m_Binding;
```

- `private readonly Game.Input.ProxyAction m_Action`  

```csharp
private readonly Game.Input.ProxyAction m_Action;
```

- `private readonly System.Action<Game.Input.ProxyBinding> m_OnChange`  

```csharp
private readonly System.Action<Game.Input.ProxyBinding> m_OnChange;
```

- `private static readonly Game.Input.ProxyBinding+Comparer comparer`  

```csharp
private static readonly Game.Input.ProxyBinding+Comparer comparer;
```


## Properties

- `public Game.Input.ProxyBinding binding { get }`  

```csharp
public Game.Input.ProxyBinding binding { get; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```


## Constructors

- `public Watcher(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onChange = null)`  

```csharp
public Watcher(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onChange);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private OnChanged(Game.Input.ProxyAction action) : System.Void`  

```csharp
private System.Void OnChanged(Game.Input.ProxyAction action);
```


