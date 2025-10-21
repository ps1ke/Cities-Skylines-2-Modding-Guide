# Game.Net.AggregateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AggregateSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Game.Net.AggregateSystem+TypeHandle __TypeHandle;

    public AggregateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Game.Net.AggregateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.AggregateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AggregateSystem()`  

```csharp
public AggregateSystem();
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

- `Game.Net.AggregateSystem+UpdateAgregatesJob`  
- `Game.Net.AggregateSystem+TypeHandle`  

