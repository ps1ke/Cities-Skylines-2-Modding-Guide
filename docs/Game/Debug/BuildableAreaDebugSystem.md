# Game.Debug.BuildableAreaDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildableAreaDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_StrictOption;
    private Colossal.Collections.NativeAccumulator<Colossal.Collections.AverageFloat> m_BuildableArea;
    private System.Single m_LastBuildableArea;
    private Game.Debug.BuildableAreaDebugSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1438325908_0;

    public System.Single buildableArea { get; }

    public BuildableAreaDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_StrictOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StrictOption;
```

- `private Colossal.Collections.NativeAccumulator<Colossal.Collections.AverageFloat> m_BuildableArea`  

```csharp
private Colossal.Collections.NativeAccumulator<Colossal.Collections.AverageFloat> m_BuildableArea;
```

- `private System.Single m_LastBuildableArea`  

```csharp
private System.Single m_LastBuildableArea;
```

- `private Game.Debug.BuildableAreaDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.BuildableAreaDebugSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1438325908_0`  

```csharp
private Unity.Entities.EntityQuery __query_1438325908_0;
```


## Properties

- `public System.Single buildableArea { get }`  

```csharp
public System.Single buildableArea { get; }
```


## Constructors

- `public BuildableAreaDebugSystem()`  

```csharp
public BuildableAreaDebugSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.BuildableAreaDebugSystem+BuildableAreaGizmoJob`  
- `Game.Debug.BuildableAreaDebugSystem+TypeHandle`  

