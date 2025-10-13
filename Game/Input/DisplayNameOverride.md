# Game.Input.DisplayNameOverride

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class DisplayNameOverride : System.IDisposable
{
    private readonly Game.Input.ProxyAction m_Action;
    private readonly System.String m_Source;
    private System.Boolean m_Disposed;
    private System.Int32 m_Priority;
    private Game.Input.UIBaseInputAction+Transform m_Transform;
    private System.String m_DisplayName;
    private System.Boolean m_Active;
    public static const System.Int32 kDisabledPriority;
    public static const System.Int32 kToolTipPriority;

    public System.String source { get; }
    public System.Boolean isDisposed { get; }
    public System.Boolean active { get; set; }
    public System.String displayName { get; set; }
    public System.Int32 priority { get; set; }
    public Game.Input.UIBaseInputAction+Transform transform { get; set; }

    public DisplayNameOverride(System.String overrideSource, Game.Input.ProxyAction action, System.String displayName, System.Int32 priority, Game.Input.UIBaseInputAction+Transform transform);

    public System.Void Dispose();
    public System.Boolean Equals(Game.Input.DisplayNameOverride other);
}
```


## Fields

- `private readonly Game.Input.ProxyAction m_Action`  

```csharp
private readonly Game.Input.ProxyAction m_Action;
```

- `private readonly System.String m_Source`  

```csharp
private readonly System.String m_Source;
```

- `private System.Boolean m_Disposed`  

```csharp
private System.Boolean m_Disposed;
```

- `private System.Int32 m_Priority`  

```csharp
private System.Int32 m_Priority;
```

- `private Game.Input.UIBaseInputAction+Transform m_Transform`  

```csharp
private Game.Input.UIBaseInputAction+Transform m_Transform;
```

- `private System.String m_DisplayName`  

```csharp
private System.String m_DisplayName;
```

- `private System.Boolean m_Active`  

```csharp
private System.Boolean m_Active;
```

- `public static const System.Int32 kDisabledPriority`  

```csharp
public static const System.Int32 kDisabledPriority;
```

- `public static const System.Int32 kToolTipPriority`  

```csharp
public static const System.Int32 kToolTipPriority;
```


## Properties

- `public System.String source { get }`  

```csharp
public System.String source { get; }
```

- `public System.Boolean isDisposed { get }`  

```csharp
public System.Boolean isDisposed { get; }
```

- `public System.Boolean active { get; set }`  

```csharp
public System.Boolean active { get; set; }
```

- `public System.String displayName { get; set }`  

```csharp
public System.String displayName { get; set; }
```

- `public System.Int32 priority { get; set }`  

```csharp
public System.Int32 priority { get; set; }
```

- `public Game.Input.UIBaseInputAction+Transform transform { get; set }`  

```csharp
public Game.Input.UIBaseInputAction+Transform transform { get; set; }
```


## Constructors

- `public DisplayNameOverride(System.String overrideSource, Game.Input.ProxyAction action, System.String displayName = null, System.Int32 priority = -1, Game.Input.UIBaseInputAction+Transform transform = None)`  

```csharp
public DisplayNameOverride(string overrideSource, ProxyAction action, string displayName = null, int priority = -1, UIBaseInputAction.Transform transform = UIBaseInputAction.Transform.None)
	{
		m_Action = action ?? throw new ArgumentNullException("action");
		m_Source = overrideSource;
		m_DisplayName = displayName;
		m_Priority = priority;
		m_Transform = transform;
		m_Action.m_DisplayOverrides.Add(this);
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
			m_Action.m_DisplayOverrides.Remove(this);
		}
	}
```

- `public Equals(Game.Input.DisplayNameOverride other) : System.Boolean`  

```csharp
public bool Equals(DisplayNameOverride other)
	{
		if (m_Priority != other.m_Priority)
		{
			return false;
		}
		if (m_DisplayName != other.m_DisplayName)
		{
			return false;
		}
		return true;
	}
```


