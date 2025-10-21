# Game.UI.InGame.TimeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TimeUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Unity.Entities.EntityQuery m_TimeSettingsQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Colossal.UI.Binding.EventBinding<System.Boolean> m_SimulationPausedBarrierBinding;
    private System.Single m_SpeedBeforePause;
    private System.Boolean m_UnpausedBeforeForcedPause;
    private System.Boolean m_HasFocus;
    private static const System.String kGroup;

    private System.Boolean pausedBarrierActive { private get; }

    public TimeUISystem();

    public System.Int32 GetDay();
    public Game.Rendering.LightingSystem+State GetLightingState();
    public System.Int32 GetSimulationSpeed();
    public System.Int32 GetTicks();
    private Game.UI.InGame.TimeUISystem+TimeSettings GetTimeSettings();
    private Game.Prefabs.TimeSettingsData GetTimeSettingsData();
    private System.Void HandleAppStateChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.AppState state);
    private static System.Single IndexToSpeed(System.Int32 index);
    public System.Boolean IsPaused();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void SetSimulationPaused(System.Boolean paused);
    private System.Void SetSimulationSpeed(System.Int32 speedIndex);
    private static System.Int32 SpeedToIndex(System.Single speed);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Unity.Entities.EntityQuery m_TimeSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Colossal.UI.Binding.EventBinding<System.Boolean> m_SimulationPausedBarrierBinding`  

```csharp
private Colossal.UI.Binding.EventBinding<System.Boolean> m_SimulationPausedBarrierBinding;
```

- `private System.Single m_SpeedBeforePause`  

```csharp
private System.Single m_SpeedBeforePause;
```

- `private System.Boolean m_UnpausedBeforeForcedPause`  

```csharp
private System.Boolean m_UnpausedBeforeForcedPause;
```

- `private System.Boolean m_HasFocus`  

```csharp
private System.Boolean m_HasFocus;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `private System.Boolean pausedBarrierActive { private get }`  

```csharp
private System.Boolean pausedBarrierActive { private get; }
```


## Constructors

- `public TimeUISystem()`  

```csharp
public TimeUISystem();
```


## Methods

- `public GetDay() : System.Int32`  

```csharp
public System.Int32 GetDay();
```

- `public GetLightingState() : Game.Rendering.LightingSystem+State`  

```csharp
public Game.Rendering.LightingSystem+State GetLightingState();
```

- `public GetSimulationSpeed() : System.Int32`  

```csharp
public System.Int32 GetSimulationSpeed();
```

- `public GetTicks() : System.Int32`  

```csharp
public System.Int32 GetTicks();
```

- `private GetTimeSettings() : Game.UI.InGame.TimeUISystem+TimeSettings`  

```csharp
private Game.UI.InGame.TimeUISystem+TimeSettings GetTimeSettings();
```

- `private GetTimeSettingsData() : Game.Prefabs.TimeSettingsData`  

```csharp
private Game.Prefabs.TimeSettingsData GetTimeSettingsData();
```

- `private HandleAppStateChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.AppState state) : System.Void`  

```csharp
private System.Void HandleAppStateChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.AppState state);
```

- `private static IndexToSpeed(System.Int32 index) : System.Single`  

```csharp
private static System.Single IndexToSpeed(System.Int32 index);
```

- `public IsPaused() : System.Boolean`  

```csharp
public System.Boolean IsPaused();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SetSimulationPaused(System.Boolean paused) : System.Void`  

```csharp
private System.Void SetSimulationPaused(System.Boolean paused);
```

- `private SetSimulationSpeed(System.Int32 speedIndex) : System.Void`  

```csharp
private System.Void SetSimulationSpeed(System.Int32 speedIndex);
```

- `private static SpeedToIndex(System.Single speed) : System.Int32`  

```csharp
private static System.Int32 SpeedToIndex(System.Single speed);
```


## Nested types

- `Game.UI.InGame.TimeUISystem+TimeSettings`  
- `Game.UI.InGame.TimeUISystem+<>c`  

