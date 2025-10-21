# Game.Buildings.SchoolUpdatedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SchoolUpdatedSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedSchoolQuery;
    private Unity.Entities.EntityQuery m_DeletedSchoolQuery;
    private Game.Buildings.SchoolUpdatedSystem+TypeHandle __TypeHandle;

    public SchoolUpdatedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedSchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedSchoolQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedSchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedSchoolQuery;
```

- `private Game.Buildings.SchoolUpdatedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.SchoolUpdatedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SchoolUpdatedSystem()`  

```csharp
public SchoolUpdatedSystem();
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

- `Game.Buildings.SchoolUpdatedSystem+SchoolUpdatedJob`  
- `Game.Buildings.SchoolUpdatedSystem+SchoolDeletedJob`  
- `Game.Buildings.SchoolUpdatedSystem+TypeHandle`  

