# Game.Input.ProxyComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public class ProxyComposite
{
    private readonly Game.Input.CompositeInstance m_Source;
    public readonly Game.Input.InputManager+DeviceType m_Device;
    public readonly Game.Input.ActionType m_Type;
    internal readonly System.Collections.Generic.HashSet<Game.Input.ProxyAction> m_LinkedActions;
    private readonly System.Collections.Generic.Dictionary<Game.Input.ActionComponent, Game.Input.ProxyBinding> m_Bindings;

    public System.Collections.Generic.IReadOnlyDictionary<Game.Input.ActionComponent, Game.Input.ProxyBinding> bindings { get; }
    public System.Boolean isSet { get; }
    public System.Boolean isBuiltIn { get; }
    internal System.Boolean isDummy { internal get; }
    internal System.Boolean isHidden { internal get; }
    public System.Boolean isRebindable { get; }
    public System.Boolean isModifiersRebindable { get; }
    public System.Boolean allowModifiers { get; }
    public System.Boolean canBeEmpty { get; }
    public System.Boolean developerOnly { get; }
    public Game.Input.Usages usage { get; }

    internal ProxyComposite(Game.Input.InputManager+DeviceType device, Game.Input.ActionType type, Game.Input.CompositeInstance source, System.Collections.Generic.IList<Game.Input.ProxyBinding> bindings);

    public virtual System.String ToString();
    public System.Boolean TryGetBinding(Game.Input.ProxyBinding sampleBinding, Game.Input.ProxyBinding& foundBinding);
    public System.Boolean TryGetBinding(Game.Input.ActionComponent component, Game.Input.ProxyBinding& foundBinding);
}
```


## Fields

- `private readonly Game.Input.CompositeInstance m_Source`  

```csharp
private readonly Game.Input.CompositeInstance m_Source;
```

- `public readonly Game.Input.InputManager+DeviceType m_Device`  

```csharp
public readonly Game.Input.InputManager+DeviceType m_Device;
```

- `public readonly Game.Input.ActionType m_Type`  

```csharp
public readonly Game.Input.ActionType m_Type;
```

- `internal readonly System.Collections.Generic.HashSet<Game.Input.ProxyAction> m_LinkedActions`  

```csharp
internal readonly System.Collections.Generic.HashSet<Game.Input.ProxyAction> m_LinkedActions;
```

- `private readonly System.Collections.Generic.Dictionary<Game.Input.ActionComponent, Game.Input.ProxyBinding> m_Bindings`  

```csharp
private readonly System.Collections.Generic.Dictionary<Game.Input.ActionComponent, Game.Input.ProxyBinding> m_Bindings;
```


## Properties

- `public System.Collections.Generic.IReadOnlyDictionary<Game.Input.ActionComponent, Game.Input.ProxyBinding> bindings { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<Game.Input.ActionComponent, Game.Input.ProxyBinding> bindings { get; }
```

- `public System.Boolean isSet { get }`  

```csharp
public System.Boolean isSet { get; }
```

- `public System.Boolean isBuiltIn { get }`  

```csharp
public System.Boolean isBuiltIn { get; }
```

- `internal System.Boolean isDummy { internal get }`  

```csharp
internal System.Boolean isDummy { internal get; }
```

- `internal System.Boolean isHidden { internal get }`  

```csharp
internal System.Boolean isHidden { internal get; }
```

- `public System.Boolean isRebindable { get }`  

```csharp
public System.Boolean isRebindable { get; }
```

- `public System.Boolean isModifiersRebindable { get }`  

```csharp
public System.Boolean isModifiersRebindable { get; }
```

- `public System.Boolean allowModifiers { get }`  

```csharp
public System.Boolean allowModifiers { get; }
```

- `public System.Boolean canBeEmpty { get }`  

```csharp
public System.Boolean canBeEmpty { get; }
```

- `public System.Boolean developerOnly { get }`  

```csharp
public System.Boolean developerOnly { get; }
```

- `public Game.Input.Usages usage { get }`  

```csharp
public Game.Input.Usages usage { get; }
```


## Constructors

- `internal ProxyComposite(Game.Input.InputManager+DeviceType device, Game.Input.ActionType type, Game.Input.CompositeInstance source, System.Collections.Generic.IList<Game.Input.ProxyBinding> bindings)`  

```csharp
internal ProxyComposite(InputManager.DeviceType device, ActionType type, CompositeInstance source, IList<ProxyBinding> bindings)
	{
		m_Device = device;
		m_Type = type;
		m_Source = source;
		foreach (ProxyBinding binding in bindings)
		{
			m_Bindings[binding.component] = binding;
		}
	}
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return $"{m_Device} ({m_Type})";
	}
```

- `public TryGetBinding(Game.Input.ProxyBinding sampleBinding, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  

```csharp
public bool TryGetBinding(ActionComponent component, out ProxyBinding foundBinding)
	{
		return m_Bindings.TryGetValue(component, out foundBinding);
	}
```

- `public TryGetBinding(Game.Input.ActionComponent component, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  

```csharp
public bool TryGetBinding(ActionComponent component, out ProxyBinding foundBinding)
	{
		return m_Bindings.TryGetValue(component, out foundBinding);
	}
```


## Nested types

- `Game.Input.ProxyComposite+Info`  
- `Game.Input.ProxyComposite+<>c`  

