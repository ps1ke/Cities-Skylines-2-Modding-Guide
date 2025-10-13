# Game.Debug.DebugWatchDistribution

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class DebugWatchDistribution : System.IDisposable
{
    private Unity.Collections.NativeQueue<System.Int32> m_RawData;
    private Unity.Jobs.JobHandle m_Deps;
    private System.Boolean m_Persistent;
    private System.Boolean m_Relative;

    public System.Boolean Persistent { get; }
    public System.Boolean Relative { get; }
    public System.Boolean IsEnabled { get; }

    public DebugWatchDistribution(System.Boolean persistent, System.Boolean relative);

    public System.Void AddWriter(Unity.Jobs.JobHandle handle);
    public System.Void Disable();
    public System.Void Dispose();
    public System.Void Enable();
    public Unity.Collections.NativeQueue<System.Int32> GetQueue(System.Boolean clear, Unity.Jobs.JobHandle& deps);
}
```


## Fields

- `private Unity.Collections.NativeQueue<System.Int32> m_RawData`  

```csharp
private Unity.Collections.NativeQueue<System.Int32> m_RawData;
```

- `private Unity.Jobs.JobHandle m_Deps`  

```csharp
private Unity.Jobs.JobHandle m_Deps;
```

- `private System.Boolean m_Persistent`  

```csharp
private System.Boolean m_Persistent;
```

- `private System.Boolean m_Relative`  

```csharp
private System.Boolean m_Relative;
```


## Properties

- `public System.Boolean Persistent { get }`  

```csharp
public System.Boolean Persistent { get; }
```

- `public System.Boolean Relative { get }`  

```csharp
public System.Boolean Relative { get; }
```

- `public System.Boolean IsEnabled { get }`  

```csharp
public System.Boolean IsEnabled { get; }
```


## Constructors

- `public DebugWatchDistribution(System.Boolean persistent = False, System.Boolean relative = False)`  

```csharp
public DebugWatchDistribution(bool persistent = false, bool relative = false)
	{
		m_Persistent = persistent;
		m_Relative = relative;
	}
```


## Methods

- `public AddWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddWriter(JobHandle handle)
	{
		if (!IsEnabled)
		{
			throw new Exception("cannot add writer to disabled DebugWatchDistribution");
		}
		m_Deps = JobHandle.CombineDependencies(m_Deps, handle);
	}
```

- `public Disable() : System.Void`  

```csharp
public void Disable()
	{
		if (IsEnabled)
		{
			m_Deps.Complete();
			m_RawData.Dispose();
		}
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		Disable();
	}
```

- `public Enable() : System.Void`  

```csharp
public void Enable()
	{
		if (!IsEnabled)
		{
			m_RawData = new NativeQueue<int>(Allocator.Persistent);
			m_Deps = default(JobHandle);
		}
	}
```

- `public GetQueue(System.Boolean clear, Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<System.Int32>`  

```csharp
public NativeQueue<int> GetQueue(bool clear, out JobHandle deps)
	{
		if (!IsEnabled)
		{
			throw new Exception("cannot get data queue from disabled DebugWatchDistribution");
		}
		if (clear)
		{
			ClearJob jobData = new ClearJob
			{
				m_RawData = m_RawData
			};
			m_Deps = jobData.Schedule(m_Deps);
		}
		deps = m_Deps;
		return m_RawData;
	}
```


## Nested types

- `Game.Debug.DebugWatchDistribution+ClearJob`  

