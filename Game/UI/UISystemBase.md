# Game.UI.UISystemBase

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public abstract class UISystemBase : Game.GameSystemBase
{
    private System.Collections.Generic.List<Colossal.UI.Binding.IBinding> m_Bindings;
    private System.Collections.Generic.List<Colossal.UI.Binding.IUpdateBinding> m_UpdateBindings;
    protected static Colossal.Logging.ILog log;

    public Game.GameMode gameMode { get; }

    protected UISystemBase();

    protected System.Void AddBinding(Colossal.UI.Binding.IBinding binding);
    protected System.Void AddUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.UI.Binding.IBinding> m_Bindings`  

```csharp
private System.Collections.Generic.List<Colossal.UI.Binding.IBinding> m_Bindings;
```

- `private System.Collections.Generic.List<Colossal.UI.Binding.IUpdateBinding> m_UpdateBindings`  

```csharp
private System.Collections.Generic.List<Colossal.UI.Binding.IUpdateBinding> m_UpdateBindings;
```

- `protected static Colossal.Logging.ILog log`  

```csharp
protected static Colossal.Logging.ILog log;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```


## Constructors

- `protected UISystemBase()`  

```csharp
[Preserve]
	protected UISystemBase()
	{
	}
```


## Methods

- `protected AddBinding(Colossal.UI.Binding.IBinding binding) : System.Void`  

```csharp
protected void AddBinding(IBinding binding)
	{
		m_Bindings.Add(binding);
		GameManager.instance.userInterface.bindings.AddBinding(binding);
	}
```

- `protected AddUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding) : System.Void`  

```csharp
protected void AddUpdateBinding(IUpdateBinding binding)
	{
		AddBinding(binding);
		m_UpdateBindings.Add(binding);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_Bindings = new List<IBinding>();
		m_UpdateBindings = new List<IUpdateBinding>();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		foreach (IBinding binding in m_Bindings)
		{
			GameManager.instance.userInterface.bindings.RemoveBinding(binding);
		}
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = (gameMode & mode) != 0;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		foreach (IUpdateBinding updateBinding in m_UpdateBindings)
		{
			updateBinding.Update();
		}
	}
```


