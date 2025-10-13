# Game.Debug.LandValueDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LandValueDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.LandValueSystem m_LandValueSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Unity.Entities.EntityQuery m_LandValueEdgeQuery;
    private Unity.Entities.EntityQuery m_LandValueParameterQuery;
    public Game.Debug.BaseDebugSystem+Option m_LandValueCellOption;
    private Game.Debug.BaseDebugSystem+Option m_EdgeLandValueOption;
    private Game.Debug.LandValueDebugSystem+TypeHandle __TypeHandle;
    private static readonly System.Single heightScale;

    public LandValueDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static UnityEngine.Color GetColor(UnityEngine.Color a, UnityEngine.Color b, UnityEngine.Color c, System.Single value, System.Single maxValue1, System.Single maxValue2);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    public virtual System.Void OnDisabled(UnityEngine.Rendering.DebugUI+Container container);
    public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.LandValueSystem m_LandValueSystem`  

```csharp
private Game.Simulation.LandValueSystem m_LandValueSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Unity.Entities.EntityQuery m_LandValueEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueEdgeQuery;
```

- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueParameterQuery;
```

- `public Game.Debug.BaseDebugSystem+Option m_LandValueCellOption`  

```csharp
public Game.Debug.BaseDebugSystem+Option m_LandValueCellOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_EdgeLandValueOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_EdgeLandValueOption;
```

- `private Game.Debug.LandValueDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.LandValueDebugSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single heightScale`  

```csharp
private static readonly System.Single heightScale;
```


## Constructors

- `public LandValueDebugSystem()`  

```csharp
public LandValueDebugSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static GetColor(UnityEngine.Color a, UnityEngine.Color b, UnityEngine.Color c, System.Single value, System.Single maxValue1, System.Single maxValue2) : UnityEngine.Color`  

```csharp
private static UnityEngine.Color GetColor(UnityEngine.Color a, UnityEngine.Color b, UnityEngine.Color c, System.Single value, System.Single maxValue1, System.Single maxValue2);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `public virtual OnDisabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public virtual System.Void OnDisabled(UnityEngine.Rendering.DebugUI+Container container);
```

- `public virtual OnEnabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.LandValueDebugSystem+LandValueEdgeGizmoJob`  
- `Game.Debug.LandValueDebugSystem+LandValueGizmoJob`  
- `Game.Debug.LandValueDebugSystem+TypeHandle`  

