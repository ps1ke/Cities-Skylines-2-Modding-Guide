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
public CheckPrefabReferencesSystem();
```


## Methods

- `public AddPrefabReferencesUser(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddPrefabReferencesUser(Unity.Jobs.JobHandle dependencies);
```

- `public BeginPrefabCheck(Unity.Collections.NativeArray<Unity.Entities.Entity> array, System.Boolean isLoading, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void BeginPrefabCheck(Unity.Collections.NativeArray<Unity.Entities.Entity> array, System.Boolean isLoading, Unity.Jobs.JobHandle dependencies);
```

- `public EndPrefabCheck(Unity.Jobs.JobHandle& dependencies) : System.Void`  

```csharp
public System.Void EndPrefabCheck(Unity.Jobs.JobHandle& dependencies);
```

- `public GetPrefabReferences(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle& dependencies) : Game.Serialization.PrefabReferences`  

```csharp
public Game.Serialization.PrefabReferences GetPrefabReferences(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle& dependencies);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Serialization.CheckPrefabReferencesSystem+CheckPrefabReferencesJob`  

