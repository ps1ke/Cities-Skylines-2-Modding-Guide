# Game.Serialization.SubRouteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubRouteSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.SubRouteSystem+TypeHandle __TypeHandle;

    public SubRouteSystem();

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

- `private Game.Serialization.SubRouteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.SubRouteSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubRouteSystem()`  

```csharp
public SubRouteSystem();
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

- `Game.Serialization.SubRouteSystem+SubNetJob`  
- `Game.Serialization.SubRouteSystem+TypeHandle`  

