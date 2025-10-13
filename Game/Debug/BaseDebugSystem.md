# Game.Debug.BaseDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public abstract class BaseDebugSystem : Game.GameSystemBase
{
    private System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> <options>k__BackingField;

    public System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> options { get; private set; }

    protected BaseDebugSystem();

    protected Game.Debug.BaseDebugSystem+Option AddOption(System.String displayName, System.Boolean defaultEnabled);
    protected virtual System.Void OnCreate();
    public virtual System.Void OnDisabled(UnityEngine.Rendering.DebugUI+Container container);
    public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
    protected virtual System.Void OnUpdate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> <options>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> <options>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> options { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> options { get; private set; }
```


## Constructors

- `protected BaseDebugSystem()`  

```csharp
[Preserve]
	protected BaseDebugSystem()
	{
	}
```


## Methods

- `protected AddOption(System.String displayName, System.Boolean defaultEnabled) : Game.Debug.BaseDebugSystem+Option`  

```csharp
protected Option AddOption(string displayName, bool defaultEnabled)
	{
		Option option = new Option(displayName, defaultEnabled);
		options.Add(option);
		return option;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		options = new List<Option>();
	}
```

- `public virtual OnDisabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public virtual void OnDisabled(DebugUI.Container container)
	{
	}
```

- `public virtual OnEnabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public virtual void OnEnabled(DebugUI.Container container)
	{
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected virtual JobHandle OnUpdate(JobHandle inputDeps)
	{
		return inputDeps;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected virtual JobHandle OnUpdate(JobHandle inputDeps)
	{
		return inputDeps;
	}
```


## Nested types

- `Game.Debug.BaseDebugSystem+Option`  

