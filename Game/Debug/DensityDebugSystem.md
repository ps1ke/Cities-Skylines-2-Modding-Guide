# Game.Debug.DensityDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DensityDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.DensityDebugSystem+TypeHandle __TypeHandle;

    public DensityDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.DensityDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.DensityDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DensityDebugSystem()`  

```csharp
public DensityDebugSystem();
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

- `Game.Debug.DensityDebugSystem+DensityGizmoJob`  
- `Game.Debug.DensityDebugSystem+TypeHandle`  

