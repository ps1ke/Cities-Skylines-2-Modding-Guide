# Game.Debug.ZoneAmbienceValueDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class ZoneAmbienceValueDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private System.Collections.Generic.Dictionary<Game.Simulation.GroupAmbienceType, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions;
    private Unity.Collections.NativeArray<UnityEngine.Color> m_DistinctColors;

    public ZoneAmbienceValueDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  

```csharp
private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private System.Collections.Generic.Dictionary<Game.Simulation.GroupAmbienceType, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions`  

```csharp
private System.Collections.Generic.Dictionary<Game.Simulation.GroupAmbienceType, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions;
```

- `private Unity.Collections.NativeArray<UnityEngine.Color> m_DistinctColors`  

```csharp
private Unity.Collections.NativeArray<UnityEngine.Color> m_DistinctColors;
```


## Constructors

- `public ZoneAmbienceValueDebugSystem()`  

```csharp
public ZoneAmbienceValueDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
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

- `Game.Debug.ZoneAmbienceValueDebugSystem+ZoneAmbienceValueGizmoJob`  

