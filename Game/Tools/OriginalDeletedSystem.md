# Game.Tools.OriginalDeletedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OriginalDeletedSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Collections.NativeArray<System.Boolean> m_OriginalDeleted;
    private Unity.Jobs.JobHandle m_Dependency;
    private Game.Tools.OriginalDeletedSystem+TypeHandle __TypeHandle;

    public OriginalDeletedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Boolean GetOriginalDeletedResult(System.Int32 delay);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_OriginalDeleted`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_OriginalDeleted;
```

- `private Unity.Jobs.JobHandle m_Dependency`  

```csharp
private Unity.Jobs.JobHandle m_Dependency;
```

- `private Game.Tools.OriginalDeletedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.OriginalDeletedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public OriginalDeletedSystem()`  

```csharp
public OriginalDeletedSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetOriginalDeletedResult(System.Int32 delay) : System.Boolean`  

```csharp
public System.Boolean GetOriginalDeletedResult(System.Int32 delay);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Tools.OriginalDeletedSystem+OriginalDeletedJob`  
- `Game.Tools.OriginalDeletedSystem+TypeHandle`  

