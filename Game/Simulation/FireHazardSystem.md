# Game.Simulation.FireHazardSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FireHazardSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_FlammableQuery;
    private Unity.Entities.EntityQuery m_FirePrefabQuery;
    private Unity.Entities.EntityQuery m_FireConfigQuery;
    private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
    private System.Single <noRainDays>k__BackingField;
    private Game.Simulation.FireHazardSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATES_PER_DAY;

    public System.Single noRainDays { get; private set; }

    public FireHazardSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_FlammableQuery`  

```csharp
private Unity.Entities.EntityQuery m_FlammableQuery;
```

- `private Unity.Entities.EntityQuery m_FirePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_FirePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_FireConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireConfigQuery;
```

- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  

```csharp
private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
```

- `private System.Single <noRainDays>k__BackingField`  

```csharp
private System.Single <noRainDays>k__BackingField;
```

- `private Game.Simulation.FireHazardSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FireHazardSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATES_PER_DAY`  

```csharp
private static const System.Int32 UPDATES_PER_DAY;
```


## Properties

- `public System.Single noRainDays { get; private set }`  

```csharp
public System.Single noRainDays { get; private set; }
```


## Constructors

- `public FireHazardSystem()`  

```csharp
public FireHazardSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
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

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.FireHazardSystem+FireHazardJob`  
- `Game.Simulation.FireHazardSystem+TypeHandle`  

