# Game.UI.InGame.TimeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Rendering.LightingSystem m_LightingSystem`  
- `private Unity.Entities.EntityQuery m_TimeSettingsQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Colossal.UI.Binding.EventBinding<System.Boolean> m_SimulationPausedBarrierBinding`  
- `private System.Single m_SpeedBeforePause`  
- `private System.Boolean m_UnpausedBeforeForcedPause`  
- `private System.Boolean m_HasFocus`  
- `private static const System.String kGroup`  

## Properties

- `private System.Boolean pausedBarrierActive { private get }`  

## Constructors

- `public TimeUISystem()`  

## Methods

- `public GetDay() : System.Int32`  
- `public GetLightingState() : Game.Rendering.LightingSystem+State`  
- `public GetSimulationSpeed() : System.Int32`  
- `public GetTicks() : System.Int32`  
- `private GetTimeSettings() : Game.UI.InGame.TimeUISystem+TimeSettings`  
- `private GetTimeSettingsData() : Game.Prefabs.TimeSettingsData`  
- `private HandleAppStateChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.AppState state) : System.Void`  
- `private static IndexToSpeed(System.Int32 index) : System.Single`  
- `public IsPaused() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SetSimulationPaused(System.Boolean paused) : System.Void`  
- `private SetSimulationSpeed(System.Int32 speedIndex) : System.Void`  
- `private static SpeedToIndex(System.Single speed) : System.Int32`  

## Nested types

- `Game.UI.InGame.TimeUISystem+TimeSettings`  
- `Game.UI.InGame.TimeUISystem+<>c`  

