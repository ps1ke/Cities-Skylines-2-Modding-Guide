# Game.Serialization.DataMigration.HomelessAndWorkerFixSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HomelessAndWorkerFixSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Unity.Entities.EntityQuery m_WorkerQuery;
    private Unity.Entities.EntityQuery m_HomelessQuery;
    private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery;
    private Unity.Entities.EntityQuery m_AbandonedPropertyQuery;
    private Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle __TypeHandle;

    public HomelessAndWorkerFixSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  

```csharp
private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
```

- `private Unity.Entities.EntityQuery m_WorkerQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkerQuery;
```

- `private Unity.Entities.EntityQuery m_HomelessQuery`  

```csharp
private Unity.Entities.EntityQuery m_HomelessQuery;
```

- `private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery;
```

- `private Unity.Entities.EntityQuery m_AbandonedPropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_AbandonedPropertyQuery;
```

- `private Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HomelessAndWorkerFixSystem()`  

```csharp
public HomelessAndWorkerFixSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+WorkerFixJob`  
- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+AddPropertySeekerJob`  
- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle`  

