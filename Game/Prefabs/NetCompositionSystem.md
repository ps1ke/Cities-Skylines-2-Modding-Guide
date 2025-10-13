# Game.Prefabs.NetCompositionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetCompositionSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CompositionQuery;
    private Game.Prefabs.NetCompositionSystem+TypeHandle __TypeHandle;

    public NetCompositionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CompositionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompositionQuery;
```

- `private Game.Prefabs.NetCompositionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NetCompositionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetCompositionSystem()`  

```csharp
public NetCompositionSystem();
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

- `Game.Prefabs.NetCompositionSystem+InitializeCompositionJob`  
- `Game.Prefabs.NetCompositionSystem+TypeHandle`  

