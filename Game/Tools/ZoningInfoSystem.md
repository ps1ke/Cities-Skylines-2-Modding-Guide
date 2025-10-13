# Game.Tools.ZoningInfoSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Tools.IZoningInfoSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoningInfoSystem : Game.GameSystemBase, Game.Tools.IZoningInfoSystem
{
    private Unity.Entities.EntityQuery m_ZoningPreferenceGroup;
    private Unity.Entities.EntityQuery m_ProcessQuery;
    private Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> m_EvaluationResults;
    private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Tools.ZoningInfoSystem+TypeHandle __TypeHandle;

    public Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> evaluationResults { get; }

    public ZoningInfoSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ZoningPreferenceGroup`  

```csharp
private Unity.Entities.EntityQuery m_ZoningPreferenceGroup;
```

- `private Unity.Entities.EntityQuery m_ProcessQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessQuery;
```

- `private Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> m_EvaluationResults`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> m_EvaluationResults;
```

- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  

```csharp
private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Tools.ZoningInfoSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ZoningInfoSystem+TypeHandle __TypeHandle;
```


## Properties

- `public Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> evaluationResults { get }`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> evaluationResults { get; }
```


## Constructors

- `public ZoningInfoSystem()`  

```csharp
public ZoningInfoSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Tools.ZoningInfoSystem+TypeHandle`  

