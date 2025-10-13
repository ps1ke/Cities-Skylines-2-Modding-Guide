# Game.Objects.RelativeBoneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RelativeBoneSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EntityQuery;
    private Game.Objects.RelativeBoneSystem+TypeHandle __TypeHandle;

    public RelativeBoneSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_EntityQuery;
```

- `private Game.Objects.RelativeBoneSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.RelativeBoneSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RelativeBoneSystem()`  

```csharp
public RelativeBoneSystem();
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

- `Game.Objects.RelativeBoneSystem+RelativeBoneJob`  
- `Game.Objects.RelativeBoneSystem+TypeHandle`  

