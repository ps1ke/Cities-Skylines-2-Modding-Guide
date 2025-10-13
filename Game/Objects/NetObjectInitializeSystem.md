# Game.Objects.NetObjectInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetObjectInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Game.Objects.NetObjectInitializeSystem+TypeHandle __TypeHandle;

    public NetObjectInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Game.Objects.NetObjectInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.NetObjectInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetObjectInitializeSystem()`  

```csharp
public NetObjectInitializeSystem();
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

- `Game.Objects.NetObjectInitializeSystem+InitializeJob`  
- `Game.Objects.NetObjectInitializeSystem+TypeHandle`  

