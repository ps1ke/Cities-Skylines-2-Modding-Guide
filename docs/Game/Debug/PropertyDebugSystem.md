# Game.Debug.PropertyDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PropertyDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_PropertyQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_ResidentialAvailableOption;
    private Game.Debug.BaseDebugSystem+Option m_ResidentialCrimeOption;
    private Game.Debug.BaseDebugSystem+Option m_CrimeOption;
    private Game.Debug.PropertyDebugSystem+TypeHandle __TypeHandle;

    public PropertyDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PropertyQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_ResidentialAvailableOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ResidentialAvailableOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ResidentialCrimeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ResidentialCrimeOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CrimeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CrimeOption;
```

- `private Game.Debug.PropertyDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.PropertyDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PropertyDebugSystem()`  

```csharp
public PropertyDebugSystem();
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

- `Game.Debug.PropertyDebugSystem+PropertyGizmoJob`  
- `Game.Debug.PropertyDebugSystem+TypeHandle`  

