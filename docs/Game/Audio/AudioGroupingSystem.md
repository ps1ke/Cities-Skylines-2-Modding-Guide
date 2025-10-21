# Game.Audio.AudioGroupingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AudioGroupingSystem : Game.GameSystemBase
{
    private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem;
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery;
    private Unity.Entities.EntityQuery m_AudioGroupingMiscSettingQuery;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_AmbienceEntities;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_NearAmbienceEntities;
    private Unity.Collections.NativeArray<Game.Prefabs.AudioGroupingSettingsData> m_Settings;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_OnFireTreeQuery;
    private Unity.Collections.NativeArray<System.Single> m_CurrentValues;
    private Game.Audio.AudioGroupingSystem+TypeHandle __TypeHandle;

    public AudioGroupingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Entities.Entity CreateEffect(Unity.Entities.Entity sfx);
    private System.Void Initialize();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
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

- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  

```csharp
private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_AudioGroupingMiscSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_AudioGroupingMiscSettingQuery;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_AmbienceEntities`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_AmbienceEntities;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_NearAmbienceEntities`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_NearAmbienceEntities;
```

- `private Unity.Collections.NativeArray<Game.Prefabs.AudioGroupingSettingsData> m_Settings`  

```csharp
private Unity.Collections.NativeArray<Game.Prefabs.AudioGroupingSettingsData> m_Settings;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_OnFireTreeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OnFireTreeQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_CurrentValues`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_CurrentValues;
```

- `private Game.Audio.AudioGroupingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Audio.AudioGroupingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AudioGroupingSystem()`  

```csharp
public AudioGroupingSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CreateEffect(Unity.Entities.Entity sfx) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity CreateEffect(Unity.Entities.Entity sfx);
```

- `private Initialize() : System.Void`  

```csharp
private System.Void Initialize();
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

- `Game.Audio.AudioGroupingSystem+AudioGroupingJob`  
- `Game.Audio.AudioGroupingSystem+TypeHandle`  

