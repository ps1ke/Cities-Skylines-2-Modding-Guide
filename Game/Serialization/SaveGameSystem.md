# Game.Serialization.SaveGameSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class SaveGameSystem : Game.GameSystemBase
{
    private System.IO.Stream <stream>k__BackingField;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> <referencedContent>k__BackingField;
    private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Serialization.WriteSystem m_WriteSystem;
    private System.Boolean m_Writing;
    private Colossal.Serialization.Entities.Context m_Context;

    public System.IO.Stream stream { get; set; }
    public Colossal.Serialization.Entities.Context context { get; set; }
    public Unity.Collections.NativeArray<Unity.Entities.Entity> referencedContent { get; set; }

    public SaveGameSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Threading.Tasks.Task RunOnce();
}
```


## Fields

- `private System.IO.Stream <stream>k__BackingField`  

```csharp
private System.IO.Stream <stream>k__BackingField;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> <referencedContent>k__BackingField`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> <referencedContent>k__BackingField;
```

- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource`  

```csharp
private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Serialization.WriteSystem m_WriteSystem`  

```csharp
private Game.Serialization.WriteSystem m_WriteSystem;
```

- `private System.Boolean m_Writing`  

```csharp
private System.Boolean m_Writing;
```

- `private Colossal.Serialization.Entities.Context m_Context`  

```csharp
private Colossal.Serialization.Entities.Context m_Context;
```


## Properties

- `public System.IO.Stream stream { get; set }`  

```csharp
public System.IO.Stream stream { get; set; }
```

- `public Colossal.Serialization.Entities.Context context { get; set }`  

```csharp
public Colossal.Serialization.Entities.Context context { get; set; }
```

- `public Unity.Collections.NativeArray<Unity.Entities.Entity> referencedContent { get; set }`  

```csharp
public Unity.Collections.NativeArray<Unity.Entities.Entity> referencedContent { get; set; }
```


## Constructors

- `public SaveGameSystem()`  

```csharp
[Preserve]
	public SaveGameSystem()
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
		m_WriteSystem = base.World.GetOrCreateSystemManaged<WriteSystem>();
		base.Enabled = false;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Context.Dispose();
		if (referencedContent.IsCreated)
		{
			referencedContent.Dispose();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_Writing)
		{
			if (m_WriteSystem.writeDependency.IsCompleted)
			{
				m_WriteSystem.writeDependency.Complete();
				m_Writing = false;
				base.Enabled = false;
				m_TaskCompletionSource?.SetResult(result: true);
			}
		}
		else
		{
			m_Writing = true;
			m_UpdateSystem.Update(SystemUpdatePhase.Serialize);
		}
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

- `Game.Serialization.SaveGameSystem+<RunOnce>d__18`  

