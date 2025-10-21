# Game.Debug.CoverageDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CoverageDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_CoverageGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private System.Collections.Generic.Dictionary<Game.Net.CoverageService, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions;
    private Game.Debug.CoverageDebugSystem+TypeHandle __TypeHandle;

    public CoverageDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CoverageGroup`  

```csharp
private Unity.Entities.EntityQuery m_CoverageGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private System.Collections.Generic.Dictionary<Game.Net.CoverageService, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions`  

```csharp
private System.Collections.Generic.Dictionary<Game.Net.CoverageService, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions;
```

- `private Game.Debug.CoverageDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.CoverageDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CoverageDebugSystem()`  

```csharp
public CoverageDebugSystem();
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

- `Game.Debug.CoverageDebugSystem+CoverageGizmoJob`  
- `Game.Debug.CoverageDebugSystem+TypeHandle`  

