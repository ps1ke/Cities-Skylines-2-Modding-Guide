# Game.Common.CleanUpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class CleanUpSystem : Game.GameSystemBase
{
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_DeletedEntities;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_UpdatedEntities;
    private Unity.Jobs.JobHandle m_DeletedDeps;
    private Unity.Jobs.JobHandle m_UpdatedDeps;
    private Unity.Entities.ComponentTypeSet m_UpdateTypes;

    public CleanUpSystem();

    public System.Void AddDeleted(Unity.Collections.NativeList<Unity.Entities.Entity> deletedEntities, Unity.Jobs.JobHandle deletedDeps);
    public System.Void AddUpdated(Unity.Collections.NativeList<Unity.Entities.Entity> updatedEntities, Unity.Jobs.JobHandle updatedDeps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_DeletedEntities`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_DeletedEntities;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_UpdatedEntities`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_UpdatedEntities;
```

- `private Unity.Jobs.JobHandle m_DeletedDeps`  

```csharp
private Unity.Jobs.JobHandle m_DeletedDeps;
```

- `private Unity.Jobs.JobHandle m_UpdatedDeps`  

```csharp
private Unity.Jobs.JobHandle m_UpdatedDeps;
```

- `private Unity.Entities.ComponentTypeSet m_UpdateTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_UpdateTypes;
```


## Constructors

- `public CleanUpSystem()`  

```csharp
public CleanUpSystem();
```


## Methods

- `public AddDeleted(Unity.Collections.NativeList<Unity.Entities.Entity> deletedEntities, Unity.Jobs.JobHandle deletedDeps) : System.Void`  

```csharp
public System.Void AddDeleted(Unity.Collections.NativeList<Unity.Entities.Entity> deletedEntities, Unity.Jobs.JobHandle deletedDeps);
```

- `public AddUpdated(Unity.Collections.NativeList<Unity.Entities.Entity> updatedEntities, Unity.Jobs.JobHandle updatedDeps) : System.Void`  

```csharp
public System.Void AddUpdated(Unity.Collections.NativeList<Unity.Entities.Entity> updatedEntities, Unity.Jobs.JobHandle updatedDeps);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


