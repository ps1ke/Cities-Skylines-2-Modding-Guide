# Game.Serialization.ResetBuildOrderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResetBuildOrderSystem : Game.GameSystemBase
{
    private Game.Tools.GenerateEdgesSystem m_GenerateEdgesSystem;
    private Unity.Entities.EntityQuery m_BuildOrderQuery;
    private Game.Serialization.ResetBuildOrderSystem+TypeHandle __TypeHandle;

    public ResetBuildOrderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.GenerateEdgesSystem m_GenerateEdgesSystem`  

```csharp
private Game.Tools.GenerateEdgesSystem m_GenerateEdgesSystem;
```

- `private Unity.Entities.EntityQuery m_BuildOrderQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildOrderQuery;
```

- `private Game.Serialization.ResetBuildOrderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ResetBuildOrderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResetBuildOrderSystem()`  

```csharp
public ResetBuildOrderSystem();
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

- `Game.Serialization.ResetBuildOrderSystem+ResetBuildOrderJob`  
- `Game.Serialization.ResetBuildOrderSystem+TypeHandle`  

