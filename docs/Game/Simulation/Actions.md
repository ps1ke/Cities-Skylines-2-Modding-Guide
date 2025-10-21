# Game.Simulation.CarNavigationSystem+Actions

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class Actions : Game.GameSystemBase
{
    private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem;
    public Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
    public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneReservation> m_LaneReservationQueue;
    public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneEffects> m_LaneEffectsQueue;
    public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneSignal> m_LaneSignalQueue;
    public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationSystem+TrafficAmbienceEffect> m_TrafficAmbienceQueue;
    public Unity.Jobs.JobHandle m_Dependency;
    private Game.Simulation.CarNavigationSystem+Actions+TypeHandle __TypeHandle;

    public Actions();

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

- `public Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  

```csharp
public Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
```

- `public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneReservation> m_LaneReservationQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneReservation> m_LaneReservationQueue;
```

- `public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneEffects> m_LaneEffectsQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneEffects> m_LaneEffectsQueue;
```

- `public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneSignal> m_LaneSignalQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneSignal> m_LaneSignalQueue;
```

- `public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationSystem+TrafficAmbienceEffect> m_TrafficAmbienceQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationSystem+TrafficAmbienceEffect> m_TrafficAmbienceQueue;
```

- `public Unity.Jobs.JobHandle m_Dependency`  

```csharp
public Unity.Jobs.JobHandle m_Dependency;
```

- `private Game.Simulation.CarNavigationSystem+Actions+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CarNavigationSystem+Actions+TypeHandle __TypeHandle;
```


## Constructors

- `public Actions()`  

```csharp
public Actions();
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

- `Game.Simulation.CarNavigationSystem+Actions+TypeHandle`  

