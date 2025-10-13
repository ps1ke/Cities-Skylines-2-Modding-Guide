# Game.Debug.RouteDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_RouteGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_RouteOption;
    private Game.Debug.BaseDebugSystem+Option m_LaneConnectionOption;
    private Game.Debug.RouteDebugSystem+TypeHandle __TypeHandle;

    public RouteDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RouteGroup`  

```csharp
private Unity.Entities.EntityQuery m_RouteGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_RouteOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_RouteOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LaneConnectionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LaneConnectionOption;
```

- `private Game.Debug.RouteDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.RouteDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteDebugSystem()`  

```csharp
public RouteDebugSystem();
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

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.RouteDebugSystem+RouteGizmoJob`  
- `Game.Debug.RouteDebugSystem+TypeHandle`  

