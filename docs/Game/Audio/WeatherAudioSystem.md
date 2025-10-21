# Game.Audio.WeatherAudioSystem

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WeatherAudioSystem : Game.GameSystemBase
{
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Unity.Entities.EntityQuery m_WeatherAudioEntityQuery;
    private Unity.Entities.Entity m_SmallWaterAudioEntity;
    private System.Int32 m_WaterAudioEnabledZoom;
    private System.Int32 m_WaterAudioNearDistance;
    private Game.Audio.WeatherAudioSystem+TypeHandle __TypeHandle;

    public WeatherAudioSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    private System.Void Initialize();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Unity.Entities.EntityQuery m_WeatherAudioEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_WeatherAudioEntityQuery;
```

- `private Unity.Entities.Entity m_SmallWaterAudioEntity`  

```csharp
private Unity.Entities.Entity m_SmallWaterAudioEntity;
```

- `private System.Int32 m_WaterAudioEnabledZoom`  

```csharp
private System.Int32 m_WaterAudioEnabledZoom;
```

- `private System.Int32 m_WaterAudioNearDistance`  

```csharp
private System.Int32 m_WaterAudioNearDistance;
```

- `private Game.Audio.WeatherAudioSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Audio.WeatherAudioSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WeatherAudioSystem()`  

```csharp
public WeatherAudioSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Audio.WeatherAudioSystem+WeatherAudioJob`  
- `Game.Audio.WeatherAudioSystem+TypeHandle`  

