# Game.Simulation.WeatherDamageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WeatherDamageSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_FacingQuery;
    private Unity.Entities.EntityQuery m_FireConfigQuery;
    private Unity.Entities.EntityQuery m_DisasterConfigQuery;
    private Unity.Entities.EntityArchetype m_DamageEventArchetype;
    private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
    private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
    private Game.Simulation.WeatherDamageSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public WeatherDamageSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_FacingQuery`  

```csharp
private Unity.Entities.EntityQuery m_FacingQuery;
```

- `private Unity.Entities.EntityQuery m_FireConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireConfigQuery;
```

- `private Unity.Entities.EntityQuery m_DisasterConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_DisasterConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DamageEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
```

- `private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData`  

```csharp
private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
```

- `private Game.Simulation.WeatherDamageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WeatherDamageSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public WeatherDamageSystem()`  

```csharp
public WeatherDamageSystem();
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

- `Game.Simulation.WeatherDamageSystem+WeatherDamageJob`  
- `Game.Simulation.WeatherDamageSystem+TypeHandle`  

