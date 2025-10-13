# Game.Objects.ResetOverriddenSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResetOverriddenSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_OverriddenQuery;
    private Game.Objects.ResetOverriddenSystem+TypeHandle __TypeHandle;

    public ResetOverriddenSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_OverriddenQuery`  

```csharp
private Unity.Entities.EntityQuery m_OverriddenQuery;
```

- `private Game.Objects.ResetOverriddenSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.ResetOverriddenSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResetOverriddenSystem()`  

```csharp
public ResetOverriddenSystem();
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

- `Game.Objects.ResetOverriddenSystem+ResetOverriddenJob`  
- `Game.Objects.ResetOverriddenSystem+TypeHandle`  

