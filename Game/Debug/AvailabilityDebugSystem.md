# Game.Debug.AvailabilityDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AvailabilityDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_AvailabilityGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private System.Collections.Generic.Dictionary<Game.Net.AvailableResource, Game.Debug.BaseDebugSystem+Option> m_AvailabilityOptions;
    private Game.Debug.AvailabilityDebugSystem+TypeHandle __TypeHandle;

    public AvailabilityDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AvailabilityGroup`  

```csharp
private Unity.Entities.EntityQuery m_AvailabilityGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private System.Collections.Generic.Dictionary<Game.Net.AvailableResource, Game.Debug.BaseDebugSystem+Option> m_AvailabilityOptions`  

```csharp
private System.Collections.Generic.Dictionary<Game.Net.AvailableResource, Game.Debug.BaseDebugSystem+Option> m_AvailabilityOptions;
```

- `private Game.Debug.AvailabilityDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.AvailabilityDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AvailabilityDebugSystem()`  

```csharp
public AvailabilityDebugSystem();
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

- `Game.Debug.AvailabilityDebugSystem+AvailabilityGizmoJob`  
- `Game.Debug.AvailabilityDebugSystem+TypeHandle`  

