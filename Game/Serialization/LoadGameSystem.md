# Game.Serialization.LoadGameSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class LoadGameSystem : Game.GameSystemBase
{
    public Game.Serialization.LoadGameSystem+EventGameLoaded onOnSaveGameLoaded;
    private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource;
    private Colossal.IO.AssetDatabase.AsyncReadDescriptor <dataDescriptor>k__BackingField;
    private Game.UpdateSystem m_UpdateSystem;
    private Colossal.Serialization.Entities.Context m_Context;

    public Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor { get; set; }
    public Colossal.Serialization.Entities.Context context { get; set; }

    public LoadGameSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Threading.Tasks.Task RunOnce();
}
```


## Fields

- `public Game.Serialization.LoadGameSystem+EventGameLoaded onOnSaveGameLoaded`  

```csharp
public Game.Serialization.LoadGameSystem+EventGameLoaded onOnSaveGameLoaded;
```

- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource`  

```csharp
private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource;
```

- `private Colossal.IO.AssetDatabase.AsyncReadDescriptor <dataDescriptor>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.AsyncReadDescriptor <dataDescriptor>k__BackingField;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Colossal.Serialization.Entities.Context m_Context`  

```csharp
private Colossal.Serialization.Entities.Context m_Context;
```


## Properties

- `public Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor { get; set; }
```

- `public Colossal.Serialization.Entities.Context context { get; set }`  

```csharp
public Colossal.Serialization.Entities.Context context { get; set; }
```


## Constructors

- `public LoadGameSystem()`  

```csharp
[Preserve]
	public LoadGameSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		base.Enabled = false;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Context.Dispose();
		onOnSaveGameLoaded = null;
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_UpdateSystem.Update(SystemUpdatePhase.Deserialize);
		base.Enabled = false;
		onOnSaveGameLoaded?.Invoke(context);
		m_TaskCompletionSource?.SetResult(result: true);
	}
```

- `public RunOnce() : System.Threading.Tasks.Task`  

```csharp
public async Task RunOnce()
	{
		m_TaskCompletionSource = new TaskCompletionSource<bool>();
		base.Enabled = true;
		await m_TaskCompletionSource.Task;
	}
```


## Nested types

- `Game.Serialization.LoadGameSystem+EventGameLoaded`  
- `Game.Serialization.LoadGameSystem+<RunOnce>d__13`  

