# Game.Simulation.GameModeNaturalResourcesAdjustSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GameModeNaturalResourcesAdjustSystem : Game.GameSystemBase
{
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    public static readonly System.Int32 kUpdatesPerDay;

    public GameModeNaturalResourcesAdjustSystem();

    private System.Void BoostStartGameNaturalResources(System.Single boostMultiplier);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public GameModeNaturalResourcesAdjustSystem()`  

```csharp
public GameModeNaturalResourcesAdjustSystem();
```


## Methods

- `private BoostStartGameNaturalResources(System.Single boostMultiplier) : System.Void`  

```csharp
private System.Void BoostStartGameNaturalResources(System.Single boostMultiplier);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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


## Nested types

- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+BoostInitialNaturalResourcesJob`  
- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+BoostInitialGroundWaterJob`  
- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+RefillNaturalResourcesJob`  

