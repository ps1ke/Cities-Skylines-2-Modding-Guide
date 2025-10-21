# Game.Buildings.InitializeSchoolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSchoolSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedSchoolQuery;
    private Unity.Entities.EntityQuery m_StudentQuery;
    private Game.Buildings.InitializeSchoolSystem+TypeHandle __TypeHandle;

    public InitializeSchoolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedSchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedSchoolQuery;
```

- `private Unity.Entities.EntityQuery m_StudentQuery`  

```csharp
private Unity.Entities.EntityQuery m_StudentQuery;
```

- `private Game.Buildings.InitializeSchoolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.InitializeSchoolSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeSchoolSystem()`  

```csharp
public InitializeSchoolSystem();
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

- `Game.Buildings.InitializeSchoolSystem+InitializeSchoolsJob`  
- `Game.Buildings.InitializeSchoolSystem+TypeHandle`  

