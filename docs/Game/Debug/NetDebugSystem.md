# Game.Debug.NetDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_NetGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_NodeOption;
    private Game.Debug.BaseDebugSystem+Option m_EdgeOption;
    private Game.Debug.BaseDebugSystem+Option m_OutlineOption;
    private Game.Debug.NetDebugSystem+TypeHandle __TypeHandle;

    public NetDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NetGroup`  

```csharp
private Unity.Entities.EntityQuery m_NetGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_NodeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_NodeOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_EdgeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_EdgeOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_OutlineOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_OutlineOption;
```

- `private Game.Debug.NetDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.NetDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetDebugSystem()`  

```csharp
public NetDebugSystem();
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

- `Game.Debug.NetDebugSystem+NetGizmoJob`  
- `Game.Debug.NetDebugSystem+TypeHandle`  

