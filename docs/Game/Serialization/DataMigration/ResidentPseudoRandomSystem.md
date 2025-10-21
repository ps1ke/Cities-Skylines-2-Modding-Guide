# Game.Serialization.DataMigration.ResidentPseudoRandomSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResidentPseudoRandomSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.DataMigration.ResidentPseudoRandomSystem+TypeHandle __TypeHandle;

    public ResidentPseudoRandomSystem();

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

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.DataMigration.ResidentPseudoRandomSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.ResidentPseudoRandomSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResidentPseudoRandomSystem()`  

```csharp
public ResidentPseudoRandomSystem();
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

- `Game.Serialization.DataMigration.ResidentPseudoRandomSystem+ResidentPseudoRandomJob`  
- `Game.Serialization.DataMigration.ResidentPseudoRandomSystem+TypeHandle`  

