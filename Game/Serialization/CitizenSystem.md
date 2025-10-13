# Game.Serialization.CitizenSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
    private Game.Serialization.CitizenSystem+TypeHandle __TypeHandle;

    public CitizenSystem();

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

- `private Unity.Entities.EntityQuery m_CitizenPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
```

- `private Game.Serialization.CitizenSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.CitizenSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CitizenSystem()`  

```csharp
public CitizenSystem();
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

- `Game.Serialization.CitizenSystem+CitizenJob`  
- `Game.Serialization.CitizenSystem+TypeHandle`  

