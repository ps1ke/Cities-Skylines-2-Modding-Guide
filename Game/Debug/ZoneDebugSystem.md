# Game.Debug.ZoneDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_BlockGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Prefabs.ZoneSystem m_ZoneSystem;
    private Game.Debug.BaseDebugSystem+Option m_PivotOption;
    private Game.Debug.BaseDebugSystem+Option m_GridOption;
    private Game.Debug.BaseDebugSystem+Option m_LotOption;
    private Game.Debug.ZoneDebugSystem+TypeHandle __TypeHandle;

    public ZoneDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BlockGroup`  

```csharp
private Unity.Entities.EntityQuery m_BlockGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Prefabs.ZoneSystem m_ZoneSystem`  

```csharp
private Game.Prefabs.ZoneSystem m_ZoneSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_PivotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PivotOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_GridOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GridOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LotOption;
```

- `private Game.Debug.ZoneDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.ZoneDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZoneDebugSystem()`  

```csharp
public ZoneDebugSystem();
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

- `Game.Debug.ZoneDebugSystem+BlockGizmoJob`  
- `Game.Debug.ZoneDebugSystem+TypeHandle`  

