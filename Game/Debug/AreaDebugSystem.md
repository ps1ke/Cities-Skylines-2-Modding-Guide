# Game.Debug.AreaDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_AreaGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_LotOption;
    private Game.Debug.BaseDebugSystem+Option m_DistrictOption;
    private Game.Debug.BaseDebugSystem+Option m_MapTileOption;
    private Game.Debug.BaseDebugSystem+Option m_SpaceOption;
    private Game.Debug.BaseDebugSystem+Option m_SurfaceOption;
    private Game.Debug.AreaDebugSystem+TypeHandle __TypeHandle;

    public AreaDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AreaGroup`  

```csharp
private Unity.Entities.EntityQuery m_AreaGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_LotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LotOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_DistrictOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_DistrictOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MapTileOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MapTileOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_SpaceOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SpaceOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_SurfaceOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SurfaceOption;
```

- `private Game.Debug.AreaDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.AreaDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaDebugSystem()`  

```csharp
public AreaDebugSystem();
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

- `Game.Debug.AreaDebugSystem+AreaGizmoJob`  
- `Game.Debug.AreaDebugSystem+TypeHandle`  

