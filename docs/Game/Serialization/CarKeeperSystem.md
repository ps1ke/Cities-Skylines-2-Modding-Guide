# Game.Serialization.CarKeeperSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CarKeeperSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Unity.Entities.EntityQuery m_KeeperQuery;
    private Game.Serialization.CarKeeperSystem+TypeHandle __TypeHandle;

    public CarKeeperSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Unity.Entities.EntityQuery m_KeeperQuery`  

```csharp
private Unity.Entities.EntityQuery m_KeeperQuery;
```

- `private Game.Serialization.CarKeeperSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.CarKeeperSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CarKeeperSystem()`  

```csharp
public CarKeeperSystem();
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

- `Game.Serialization.CarKeeperSystem+CarKeeperJob`  
- `Game.Serialization.CarKeeperSystem+NoCarJob`  
- `Game.Serialization.CarKeeperSystem+TypeHandle`  

