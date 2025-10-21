# Game.Debug.AudioGroupingDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AudioGroupingDebugSystem : Game.GameSystemBase
{
    private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem;
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery;
    private Game.Debug.AudioGroupingDebugSystem+TypeHandle __TypeHandle;

    public AudioGroupingDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem`  

```csharp
private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem;
```

- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  

```csharp
private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery;
```

- `private Game.Debug.AudioGroupingDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.AudioGroupingDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AudioGroupingDebugSystem()`  

```csharp
public AudioGroupingDebugSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Debug.AudioGroupingDebugSystem+AudioGroupingGizmoJob`  
- `Game.Debug.AudioGroupingDebugSystem+TypeHandle`  

