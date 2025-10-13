# Game.Objects.DamageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DamageSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Game.Objects.DamageSystem+TypeHandle __TypeHandle;

    public DamageSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Game.Objects.DamageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.DamageSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DamageSystem()`  

```csharp
public DamageSystem();
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

- `Game.Objects.DamageSystem+DamageObjectsJob`  
- `Game.Objects.DamageSystem+TypeHandle`  

