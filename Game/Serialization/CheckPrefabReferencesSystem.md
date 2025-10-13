# Game.Serialization.CheckPrefabReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CheckPrefabReferencesSystem : Game.GameSystemBase
{
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray;
    private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs;
    private Unity.Jobs.JobHandle m_DataDeps;
    private Unity.Jobs.JobHandle m_UserDeps;
    private System.Boolean m_IsLoading;

    public CheckPrefabReferencesSystem();

    public System.Void AddPrefabReferencesUser(Unity.Jobs.JobHandle dependencies);
    public System.Void BeginPrefabCheck(Unity.Collections.NativeArray<Unity.Entities.Entity> array, System.Boolean isLoading, Unity.Jobs.JobHandle dependencies);
    public System.Void EndPrefabCheck(Unity.Jobs.JobHandle& dependencies);
    public Game.Serialization.PrefabReferences GetPrefabReferences(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray;
```

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs;
```

- `private Unity.Jobs.JobHandle m_DataDeps`  

```csharp
private Unity.Jobs.JobHandle m_DataDeps;
```

- `private Unity.Jobs.JobHandle m_UserDeps`  

```csharp
private Unity.Jobs.JobHandle m_UserDeps;
```

- `private System.Boolean m_IsLoading`  

```csharp
private System.Boolean m_IsLoading;
```


## Constructors

- `public CheckPrefabReferencesSystem()`  

```csharp
[Preserve]
	public CheckPrefabReferencesSystem()
	{
	}
```


## Methods

- `public AddPrefabReferencesUser(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void AddPrefabReferencesUser(JobHandle dependencies)
	{
		m_UserDeps = JobHandle.CombineDependencies(m_UserDeps, dependencies);
	}
```

- `public BeginPrefabCheck(Unity.Collections.NativeArray<Unity.Entities.Entity> array, System.Boolean isLoading, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void BeginPrefabCheck(NativeArray<Entity> array, bool isLoading, JobHandle dependencies)
	{
		m_PrefabArray = array;
		m_ReferencedPrefabs = new UnsafeList<bool>(0, Allocator.TempJob);
		m_ReferencedPrefabs.Resize(array.Length, NativeArrayOptions.ClearMemory);
		m_DataDeps = dependencies;
		m_IsLoading = isLoading;
	}
```

- `public EndPrefabCheck(Unity.Jobs.JobHandle& dependencies) : System.Void`  

```csharp
public void EndPrefabCheck(out JobHandle dependencies)
	{
		dependencies = JobHandle.CombineDependencies(m_DataDeps, m_UserDeps);
		m_ReferencedPrefabs.Dispose(dependencies);
		m_PrefabArray = default(NativeArray<Entity>);
		m_ReferencedPrefabs = default(UnsafeList<bool>);
		m_DataDeps = default(JobHandle);
		m_UserDeps = default(JobHandle);
	}
```

- `public GetPrefabReferences(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle& dependencies) : Game.Serialization.PrefabReferences`  

```csharp
public PrefabReferences GetPrefabReferences(SystemBase system, out JobHandle dependencies)
	{
		dependencies = m_DataDeps;
		return new PrefabReferences(m_PrefabArray, m_ReferencedPrefabs, system.GetComponentLookup<PrefabData>(isReadOnly: true), m_IsLoading);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.Dependency = (m_UserDeps = (m_DataDeps = IJobParallelForExtensions.Schedule(new CheckPrefabReferencesJob
		{
			m_PrefabArray = m_PrefabArray,
			m_PrefabData = GetComponentLookup<PrefabData>(),
			m_ReferencedPrefabs = m_ReferencedPrefabs
		}, m_PrefabArray.Length, 64, JobHandle.CombineDependencies(m_DataDeps, m_UserDeps, base.Dependency))));
	}
```


## Nested types

- `Game.Serialization.CheckPrefabReferencesSystem+CheckPrefabReferencesJob`  

